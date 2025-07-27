# My Homebrew Setup Backup

![Built with Homebrew](https://img.shields.io/badge/Built%20with-Homebrew-blue?style=flat-square&logo=homebrew&logoColor=white)
![Managed with Brew Bundle](https://img.shields.io/badge/Managed%20with-Brew%20Bundle-orange?style=flat-square&logo=homebrew&logoColor=white)
![Workflow Status](https://github.com/KnowOneActual/Homebrew_Brewfile/actions/workflows/YOUR_WORKFLOW_FILE_NAME.yml/badge.svg)

This repository helps me keep my Homebrew package installations backed up and easily reproducible across different machines or after fresh macOS installations. It uses `brew bundle` to manage my Homebrew formulae, casks, and even Mac App Store applications.

-----

## How It Works

Homebrew's `brew bundle` command creates a `Brewfile` which lists all your installed Homebrew packages, casks, and optionally Mac App Store apps. This file acts as a snapshot of your development environment.

### 1\. Generating Your Brewfile

To create or update your `Brewfile` with your current Homebrew setup, open your terminal and run:

```bash
brew bundle dump --force
```

Using `--force` ensures that if a `Brewfile` already exists, it gets overwritten with the latest list of your installed software. This command will save the `Brewfile` in the root of this repository.

### 2\. Backing Up Your Brewfile

Once generated, commit the `Brewfile` to this GitHub repository. This effectively backs up your Homebrew configuration to the cloud.

```bash
git add Brewfile
git commit -m "Update Brewfile with latest installed packages"
git push origin main
```

### 3\. Restoring Your Homebrew Setup

When you're on a new machine, or after a fresh macOS install, you can restore your entire Homebrew setup by cloning this repository and running `brew bundle`.

First, make sure Homebrew is installed. If not, you can install it with:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Then, clone this repository:

```bash
git clone [YOUR_REPOSITORY_URL]
cd [YOUR_REPOSITORY_NAME]
```

Finally, run `brew bundle` to install everything listed in your `Brewfile`:

```bash
brew bundle
```

This command will read your `Brewfile` and automatically install all the listed taps, formulae, casks, and Mac App Store applications, getting your development environment ready quickly.

-----

## Why Use This?

  * **Consistency:** Ensures all your development machines have the same essential software.
  * **Efficiency:** Quickly set up a new machine without manually installing each application.
  * **Version Control:** Track changes to your installed software over time directly within Git.

-----

### Customizing Your Brewfile

You can manually edit the `Brewfile` to exclude certain items or add specific taps or repositories that aren't automatically included by `brew bundle dump`. Just be sure to run `brew bundle dump --force` again if you want to capture new installations automatically.

-----
