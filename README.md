> [!IMPORTANT]
> This extension is temporary.
> 
> It allows using Mago with GrumPHP in a simple (though somewhat unconventional) way while waiting for the merge of [this PR](https://github.com/phpro/grumphp/pull/1216) into a release.
> 
> Once that happens, this extension will become outdated.

# Description

This repository adds a task for GrumPHP that launches [mago](https://github.com/carthage-software/mago).
During a commit check for PHP improvements. If a tool fails, it won't pass.


# Installation

Install it using composer:

```composer require --dev johnatas-x/grumphp-mago```


# Usage

1) Add the extension in your grumphp.yml file:
```yaml
extensions:
  - GrumphpMago\ExtensionLoader
```

2) Add mago to the tasks (the example below shows default values):
```
tasks:
  mago:
    formatter: true
    formatter_options: ['--staged']
    linter: true
    linter_options: ['--staged']
    analyzer: true
    analyzer_options: ['--staged']
    guard: false
    guard_options: []
```

- **formatter** (bool): Enable the formatter tool.
- **formatter_options** (array): List of options to pass to the formatter tool.
- **linter** (bool): Enable the linter tool.
- **linter_options** (array): List of options to pass to the linter tool.
- **analyzer** (bool): Enable the analyzer tool.
- **analyzer_options** (array): List of options to pass to the analyzer tool.
- **guard** (bool): Enable the architectural guard tool.
- **guard_options** (array): List of options to pass to the architectural guard tool.

> [!CAUTION]
>
> You must have the mago [configuration file](https://mago.carthage.software/guide/configuration#configuration-file-discovery) in your project.
>
> The paths must be defined in the configuration file.
