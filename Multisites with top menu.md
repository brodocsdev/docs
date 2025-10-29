# Multisites


You can create multisites where each top menu link directs to new site with own left menu structure. Therefore you can combine different areas, like e.. requirement management, architectures, docs of microservices, terraform modules, etc., into single docs portal. 

Here is some [TeamB](https://mvp.brodocs.io/21a3986b137fb8f4ff8/Backlog/README.html) site example with flat menu build from two public repositories, one is open source project [https://github.com/MrLesk/Backlog.md](https://github.com/MrLesk/Backlog.md), second this repository.

Second [Enterprise site](https://mvp.brodocs.io/94c8be738065bd0c559/Backlog/Intakebacklog/README.html) example has some more hierarchical menu structure, still each menu item directs to separate site with own structure. 

To construct multisites simple yaml file is needed. Bellow definitions of both examples. Save the file on disk, e.g. `cat > ./teamB.yaml`, and send it via curl. If any of repo is private, add key as parameter. 



## Simple [site](https://mvp.brodocs.io/21a3986b137fb8f4ff8/Backlog/README.html) with top menu bar

Create yaml file:

```yaml

email: ...
name: TeamB
repos:
  - name: docs
    cloneUrl: https://github.com/brodocsdev/docs.git
  - name: backlogmd
    cloneUrl: https://github.com/MrLesk/Backlog.md.git

menus:
  - name: Backlog
    target: README.html
    repo:
      name: backlogmd
  - name: Docs
    target: README.html
    repo:
      name: docs

```

and POST it (with key if any repo is private)

```sh

curl -X POST 'https://mvp.brodocs.io/api/sites/init' -F "yaml=@./teamB.yaml;type=application/x-yaml" -F "key=...."

```


## Company wide [site](https://mvp.brodocs.io/94c8be738065bd0c559/Backlog/Intakebacklog/README.html) with top menu hierarchy

Create yaml file:

```yaml

email: ...
name: Enterprise site
repos:
  - name: repo1
    cloneUrl: https://github.com/brodocsdev/repo1.git
  - name: repo2
    cloneUrl: https://github.com/brodocsdev/repo2.git
  - name: repo3
    cloneUrl: https://github.com/brodocsdev/repo3.git
  - name: repo4
    cloneUrl: https://github.com/brodocsdev/repo4.git
  - name: repo5
    cloneUrl: https://github.com/brodocsdev/repo5.git
  - name: repo6
    cloneUrl: https://github.com/brodocsdev/repo6.git
  - name: repo7
    cloneUrl: https://github.com/brodocsdev/repo7.git
  - name: repo8
    cloneUrl: https://github.com/brodocsdev/repo8.git

menus:
  - name: Backlog
    menus:
      - name: Intake
        target: README.html
        repo:
          name: repo1
      - name: Product backlog
        target: README.html
        repo:
          name: repo2
  - name: Architecture
    menus:
      - name: ADRs
        target: README.html
        repo:
          name: repo3
      - name: Landscape
        target: README.html
        repo:
          name: repo4
      - name: Platform
        target: README.html
        repo:
          name: repo5
  - name: Services
    menus:
      - name: Service A
        target: README.html
        repo:
          name: repo6
      - name: Service B
        target: README.html
        repo:
          name: repo7

  - name: Infrastructure
    menus:
      - name: Cloud docs
        target: README.html
        repo:
          name: repo8
      - name: Terraform modules
        target: README.html
        repo:
          name: repo8
      - name: Ansible roles
        target: README.html
        repo:
          name: repo8


```

and POST it (with key if any repo is private):

```sh

curl -X POST 'https://mvp.brodocs.io/api/sites/init' -F "yaml=@./companySite.yaml;type=application/x-yaml" -F "key=...."

```