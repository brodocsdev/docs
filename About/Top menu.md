# Top Menu

The top menu gives your site its main navigation — the bar that appears at the top of every page. Brodocs builds it automatically from your repository structure, so there is nothing to configure manually.


## How it works

When `autoTopMenu: true` is set in `.brodocs/config.yaml`, Brodocs uses the **first-level directories** in your repository as top menu items. Each directory becomes one menu entry, and clicking it takes the visitor to the left-menu sub-site built from that directory's contents.

For the site you are reading now, the repository has two top-level directories — `About` and `Updates` — which is why you see exactly those two items in the top bar.


## Enabling the top menu

Open (or create) `.brodocs/config.yaml` in your repository and add the flag:

```yaml
autoTopMenu: true
```

Full minimal example:

```yaml
autoTopMenu: true
ui:
  tittle: My Docs
  colors: dark
  centerMenu: true  # optional, centers the top menu; default is false (left-aligned)
```

Push the change and Brodocs will pick it up on the next build.


## Controlling the order of top menu items

The order of top menu items follows the same rules as the left menu — there is nothing separate to learn. Use either of the two standard approaches:

**Order file** — create a plain text file named `order` in the root of your repository and list the directory names in the order you want them to appear:

```plain
About
Updates
```

**Explorer Sort VS Code plugin** — drag the top-level directories in the VS Code Explorer panel into the desired order. The extension writes the order to `.vscode/settings.json`, which Brodocs reads automatically. See [Controlling order](/About/Controlling%20order.md) for full details on both options.


## What becomes a top menu item

Only **first-level directories** are picked up. Files at the root level and nested subdirectories are ignored for top menu purposes. Each directory that appears in the top menu gets its own left-menu sub-site built from its contents, exactly as if it were a standalone site.

There is no depth limit for the left menu within each section — only the first level is used for the top bar.


## Multi-repo top menu

For internal portals it is also possible to build a top menu from **multiple separate repositories**, where each repo maps to one top menu section. This is more suited to team or enterprise setups where different teams own different repos. Since the current focus is on public docs for founders, that setup is not covered in detail here — reach out to **founder@brodocs.io** if you need it.
