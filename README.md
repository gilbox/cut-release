# fork info

This is a fork of `cut-release` it includes all the features of cut-release
except that **it always assumes you're in a git repo** and
when it creates a git tag instead of tagging with just the version, it
tags with

    <package-name>@<version>

The reason to do this is when you want to manage multiple npm packages
in a single repo. In this case you need to avoid tag name conflicts and this accomplishes
that in the simplest way.

# cut-private-release

A command line tool that helps you make faster npm releases.

![](https://raw.githubusercontent.com/bjoerge/cut-release/master/demo.gif)

# What it does:

  * runs `npm version` with the version you specify. If run in a git repo, it will also create a version commit and tag, just like what [`npm version`](https://docs.npmjs.com/cli/version) does.
  * pushes commits and tags to origin
  * runs `npm publish`

# Install

    npm install -g gilbox-cut-release

# Usage 

```
Usage: gilbox-cut-release [<newversion> | patch | minor | major | prepatch | preminor | premajor | prerelease]


  Options:

    --yes, -y       Don't confirm, just release right away. The new version must be supplied.

    --message, -m   If supplied, npm will use it as a commit message when
                    creating a version commit. If the message contains %s then
                    that will be replaced with the resulting version number
```
