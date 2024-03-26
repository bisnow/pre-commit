# pre-commit

This repository contains [pre-commit](https://pre-commit.com) hooks that can be used in any project.

- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
    - [Disabling Hooks](#disabling-hooks)
- [Available Hooks](#available-hooks)
    - [php-cs-fixer](#php-cs-fixer)
    - [phpstan](#phpstan)
    - [pint](#pint)

## Installation

Install the pre-commit framework:

```bash
brew install pre-commit
```

## Configuration

Create a file named `.pre-commit-config.yaml` file in the root of your project:

```bash
touch .pre-commit-config.yaml
```

Configure [the hooks](#available-hooks) you would like to use:

```yaml
repos:
  - repo: https://github.com/bisnow/pre-commit
    rev: v1.0.0
    hooks:
      - id: php-cs-fixer
      - id: phpstan
```

Install the Git hook scripts:

```bash
pre-commit install
```

Optionally, run the hooks against all files:

```bash
pre-commit run --all-files
```

## Usage

After you've configured and installed the Git hook scripts, pre-commit will run on every commit.

You can manually run all the hooks:

```bash
pre-commit run --all-files
```

Or run a specific hook:

```bash
pre-commit run pint
```

### Disabling Hooks

You can temporarily disable hooks by adding the `--no-verify` flag to your `git` command:

```bash
git commit --no-verify -m "wip"
```

Or by setting the `SKIP` environment variable:

```bash
SKIP=phpstan,pint git commit -m "wip"
```

## Available Hooks

### php-cs-fixer

Runs [PHP-CS-Fixer](https://cs.symfony.com) on your project.

### phpstan

Runs [PHPStan](https://phpstan.org) on your project.

### pint

Runs [Laravel Pint](https://laravel.com/docs/master/pint) on your project.
