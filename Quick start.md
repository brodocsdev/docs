
# How to test it

To get site like this you are currently seeing you need to simply curl clone url, name and your email as post params. No account creation is needed now.

```sh

curl -X POST 'https://mvp.brodocs.io/api/sites/init' -F "email=..." -F "name=Test site" -F "repo=https://github.com/brodocsdev/docs.git"

```

You should see output like this:

```plain
Started. Your userId is: ef1....

...

Site index.html: https://mvp.brodocs.io/ef1.../index.html
Site generate in: 574ms
```

The userId (equals site id) is hash of your email and site name (e.g `echo -n 'mail@mail.com/First site' | md5sum | cut -c1-19`). If the git repo is private, create a dedicated token with your repository provider and pass it as another POST parameter when calling init.
```sh
curl -X POST ... -F "key=ghp_abcd..."
```


The key is not stored, so you need to provide it again when sending a site update request. If you see a `Server busy message`, try again in a minute. There is a limit on concurrent site builds to prevent overloading this single-instance server 😎, which handles both site builds and serving static files

## Multiple repositories

You may want to add more repositories of your micro (nano 😎) repos. They all will be visible on left pane menu, e.g. [TeamA](https://mvp.brodocs.io/d60fbef37ec4500a30a/docs/README.html):
```sh
curl -X POST 'https://mvp.brodocs.io/api/sites/init' -F "email=..." -F "name=TeamA" -F "repo=https://github.com/MrLesk/Backlog.md.git" -F "repo=https://github.com/brodocsdev/docs.git"
```


or you may want to construct multisite with top menu from multiple repos, then some simple [yaml manifest is needed](/Multisites%20with%20top%20menu.md).



## Updates

When you push some updates, send update request via curl
```sh
curl -X POST 'https://mvp.brodocs.io/api/sites/ef1.../pull' -F "key=ghp_abcd..."
```


or setup proper repo provider action, e.g [github action](/Updates.md). 
