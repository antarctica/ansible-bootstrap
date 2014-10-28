# Bootstrap (`bootstrap`)

**Part of the BAS Ansible Role Collection (BARC)**

Performs minimal configuration required to enable management of a node by automated tools

## Overview

* Configures passwordless sudo for ease of use from the terminal and when using automated tools (such as ansible).
* Unless disabled, creates a new OS user, 'controller' for performing privileged actions (such as `apt-get install`) using sudo. Designed for use from the terminal and when using automated tools (such as ansible). The `authorized_keys` file for the user is set to contain any file in the `bootstrap_controller_user_authorized_keys_directory` directory.

## Author

[British Antarctic Survey](http://www.antarctica.ac.uk) - Web & Applications Team

Contact: [basweb@bas.ac.uk](mailto:basweb@bas.ac.uk).

## Availability

This role is designed for internal use but if useful can be shared publicly.

## Branches

This project uses three permanent branches with the *Git Flow* branching model managing the interaction between branches.

* **Develop:** unstable, potentially non-working but most current version of roles. Bug fixes and features interact with this branch only.
* **Master:** stable, tested, working version of role with full documentation. Releases and hot fixes mainly interact with this branch. This branch should when consuming roles internally.
* **Public:** equivalent to the *master* branch, but available externally. Some configuration details may be altered or features removed to make available for public release.

## Testing

Manual testing is performed for all roles to ensure roles achieve their aims and this forms a prerequisite task for merging changes into the *master* and *public* branches.
Wherever possible testing is as complete as possible meaning tasks such as downloading dependencies are performed as part of each test.

## Issues

Please log issues to the [BAS Web and Applications Team](https://jira.ceh.ac.uk/browse/BASWEB) project in Jira, within the *Project - Ansible Roles* component.

If outside of NERC please get in touch to report any issues.

## Contributions

We have no formal contribution policy, if you spot any bugs or potential improvements please submit a pull request or get in touch.

These roles are used for internal projects which may dictate whether any contributions can be included.

## License

[Open Government Licence V2](https://www.nationalarchives.gov.uk/doc/open-government-licence/version/2/)

## Requirements

### Other requirements

* Public keys which should be added to the `authorized_keys` file of the controller user, each key should be a separate file. Keys should be contained in  `bootstrap_controller_user_authorized_keys_directory`.

## Variables

* `bootstrap_controller_user_authorized_keys_directory`
	* Path relative to where this role is installed to the directory that contains files for the `authorized_keys` file of the controller user.
	* This variable **must** point to a directory, it **must not** include a trailing `/`.
	* Default: "../../../public_keys"

## Changelog

### 0.1.2 - October 2014

* Creation of controller user is now optional though enabled by default
* The controller user's username is now configurable, if enabled
* Preparing role for public release

### 0.1.1 - September 2014

* Adjusting role for inclusion in BARC

### 0.1.0 - June 2014

* Initial version
