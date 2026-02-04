# puppetlib

A collection of reusable Puppet manifests, classes, and helper functions to standardize configuration across your infrastructure.

## Table of contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Examples](#examples)
- [Testing](#testing)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

## Overview

`puppetlib` is a library-style Puppet module intended to hold shared manifests, defined types, functions, and common patterns used across other Puppet modules in an organization. It aims to centralize common code and make modules easier to maintain.

## Features

- Shared helper classes and defined types
- Utility functions and data providers
- Conventions for parameter validation and logging
- Reusable manifests for common OS configuration tasks

*(Customize this list to reflect the actual functionality provided by the repository.)*

## Requirements

- Puppet: >= X.Y.Z (replace with actual supported versions)
- Facter: >= X.Y.Z
- Supported OS: e.g. Debian/Ubuntu, RHEL/CentOS, Amazon Linux (replace with actual platforms)
- Ruby: >= X.Y (if the module includes Ruby functions)

## Installation

You can consume this repository in several ways:

- With r10k or Code Manager (Puppetfile):
  ```
  mod 'puppetlib', :git => 'https://github.com/rambejjanki/puppetlib.git', :ref => 'main'
  ```

- As a git submodule:
  ```
  git submodule add https://github.com/rambejjanki/puppetlib.git modules/puppetlib
  ```

- Directly clone:
  ```
  git clone https://github.com/rambejjanki/puppetlib.git
  ```

## Usage

Include classes or instantiate defined types from this module in your site manifests or other modules.

Example (top-scope include):
```puppet
include puppetlib
```

Example (class with parameters):
```puppet
class { 'puppetlib::example':
  param1 => 'value',
  enable => true,
}
```

Hiera integration (if the module supports Hiera lookups):
```yaml
puppetlib::example::param1: 'value'
puppetlib::example::enable: true
```

*(Replace `puppetlib::example` with real classes/defined types from the repo.)*

## Examples

Provide short, copy-pasteable examples for common use-cases here. For example:

- Configuring a shared user account
- Managing a central configuration file
- Providing a helper defined type to manage service templates

## Testing

We recommend the standard Puppet module testing stack. Typical commands:

- Install dependencies:
  ```
  bundle install
  ```

- Run unit tests:
  ```
  bundle exec rake spec
  ```

- Run linting:
  ```
  bundle exec rake rubocop
  bundle exec rake puppet_lint
  ```

- Run acceptance tests (if any, e.g. with Test Kitchen):
  ```
  kitchen test
  ```

*(Adjust according to the actual test tooling present in the repo — rspec-puppet, puppet-lint, rubocop, kitchen, etc.)*

## Development

- Fork the repo and create a feature branch.
- Add tests for new behavior before implementing it.
- Run the full test suite locally before submitting a PR.

Suggested developer workflow:
```bash
git checkout -b feature/my-new-helper
# make changes
bundle install
bundle exec rake spec
# push and open a PR
```

## Contributing

Contributions are welcome! Please:

1. Open an issue to discuss large changes.
2. Follow the coding and testing conventions in the repository.
3. Ensure tests pass and add/modify tests for new features or bug fixes.
4. Create a pull request with a clear description of changes.

Include guidelines for commit messages and branch naming if you have a convention.

## License

Specify the license here (e.g. MIT, Apache-2.0). If unknown, add a LICENSE file to the repository and update this section accordingly.

---