
## Public vs private repos

To send push notification for public repos, the repo provider native way of sending notifications is sufficient, e.g. Github Webhooks, just call pull url with site id:

```plain
https://mvp.brodocs.io/api/sites/ef1.../pull
```


For private repos, since the key is not stored and providers generally do not allow to use secrets in notifications, some simple CI/CD pipeline is needed. Support for OAuth 2.0 + HMAC will come later.


## Github action example

Create secret BRODOCS_GH_KEY with dedicated key and create simple action:

```yaml
name: Update brodocs
on:
  push:
    branches:
      - main
      - master
  pull_request:
    branches: [ "main" ]

jobs:
  call-brodocs:
    runs-on: ubuntu-latest
    steps:
      - name: Call brodocs URL
        run: |
          response=$(curl -s -w "%{http_code}" -o brodocs_response.txt -X POST \
            -F "key=${{ secrets.BRODOCS_GH_KEY }}" \
            "https://mvp.brodocs.io/api/sites/ef1.../pull")
          if [ "$response" -ne 200 ]; then
            echo "Request failed with status $response"
            cat brodocs_response.txt
            exit 1
          fi
          cat brodocs_response.txt
```