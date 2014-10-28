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

### 0.1.1 - September 2014

* Adjusting role for inclusion in BARC

### 0.1.0 - June 2014

* Initial version
