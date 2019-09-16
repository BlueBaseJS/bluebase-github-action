# BlueBase for GitHub Actions

Use BlueBase CLI with GitHub Actions!
This repository contains a prebuilt base image with GitHub Actions implementations.

## What's inside?

Within this BlueBase CLI action, you have full access to the original BlueBase CLI.
That means you can perform any command like login, publish and build.

### Why use a base-image?

Every GitHub action will start from scratch using the dockerfile as the starting point.
If you define `@bluebase/cli` in this dockerfile, it will install it every time you run an action.
By using a prebuilt image, it basically "skips" the process of downloading the full CLI over and over again.
This makes the BlueBase actions overall faster.

## Example workflows

Before you dive into the workflow examples, you should know the basics of GitHub Actions.
You can read more about this in the [GitHub Actions documentation][link-actions].

### Installing a BlueBase CLI Plugin

To install a cli plugin see the following example.

```yml
- name: Install BlueBase Web Plugin
  uses: BlueBaseJS/bluebase-github-action@master
  with:
    args: plugins:add @bluebase/cli-expo
```

### Building Expo

To build an expo project see the following example:

```yml
- name: Build Expo
	uses: BlueBaseJS/bluebase-github-action@master
  with:
    args: expo:build
```

[link-actions]: https://developer.github.com/actions/
