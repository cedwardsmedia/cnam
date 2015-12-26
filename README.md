# CNAM v1.4.0

[![Source](https://img.shields.io/badge/source-cedwardsmedia/cnam-blue.svg?style=flat-square "Source")](https://www.github.com/cedwardsmedia/cnam)
![Version](https://img.shields.io/badge/version-1.4.0-brightgreen.svg?style=flat-square)
[![License](https://img.shields.io/badge/license-MIT-lightgrey.svg?style=flat-square "License")](./LICENSE)
[![Gratipay](https://img.shields.io/gratipay/cedwardsmedia.svg?style=flat-square "License")](https://gratipay.com/~cedwardsmedia/)

![CNAM Screenshot](https://cdn.cedwardsmedia.com/images/cnam/screenshot.png "CNAM Screenshot")

_CNAM_ is a web-based reverse phone number lookup tool written in PHP and sourced by [EveryoneAPI](https://www.everyoneapi.com/). In order to use CNAM, you must have an [EveryoneAPI account](https://www.everyoneapi.com/sign-up)  with [available funds](https://www.everyoneapi.com/pricing).

## Installation

For **personal** or **private** use:

1. Clone the repo.
2. Run `php composer.phar install`
3. Rename `config.default.php` to `config.php`.
4. Edit `config.php` and add your EveryoneAPI credentials.
5. Point your browser to index.php and enter a valid 10-digit United States or Canada phone number and click the ![Search](https://cdn.cedwardsmedia.com/images/cnam/search.png "Search") button or press enter.

For **public** use:

1. Clone the repo.
2. Run `php composer.phar install`
3. Point your browser to index.php
4. Click the ![Settings](https://cdn.cedwardsmedia.com/images/cnam/cog.png "Settings") icon
5. Enter your EveryoneAPI credentials and click "save changes"
6. Enter a valid 10-digit United States or Canada phone number and click the ![Search](https://cdn.cedwardsmedia.com/images/cnam/search.png "Search") button or press enter.

# Command-line client
cnam.php offers a command-line client to the EveryoneAPI service. Currently, it piggybacks off the same config and API class as the web-based client. Before using the CLI client, make sure it is executable by running `chmod +x /path/to/cnam.php`.

To perform a lookup of a phone number: `php /path/to/cnam.php [phonenumber] [--name]`

**Note:** for easier usage, you may wish to create a symlink to cnam.php. To do this, simply execute `sudo ln -s /path/to/cnam.php /usr/local/cnam`. Now, you can execute cnam by simply running `cnam [phone number]` without including the path to cnam.php.

### Data Point Flags

Running `cnam <phone_number>` without specifying any data point flags will cause CNAM to return all available data for the provided number.

Providing one or more data point flags will cause CNAM to return ONLY the selected data points. Example: `cnam 5551234567 --name --carrier` will cause CNAM to return only the name and carrier for the provided number.

- Use the `--name` flag to query for the *name* data point.
- Use the `--profile` flag to query for the *profile* data point.
- Use the `--cnam` flag to query for the *cnam* data point.
- Use the `--gender` flag to query for the *gender* data point.
- Use the `--image` flag to query for the *image* data point.
- Use the `--address` flag to query for the *address* data point.
- Use the `--location` flag to query for the *location* data point. (Included free with `--address`)
- Use the `--provider` flag to query for the *provider* data point.
- Use the `--carrier` flag to query for the *carrier* data point.
- Use the `--carrier_o` flag to query for the *carrier_o* data point. (Included free with `--carrier`)
- Use the `--linetype` flag to query for the *linetype* data point.



## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request ^^,

## Known Issues:

1. Apple Contacts, Google Contacts, and others do not import avatar from exported vCard. This is an issue with the way these products parse vCard documents and is NOT a bug in CNAM. However, in the interest of interoperability, I will add base64 encoded images to the vCard format in a future release.
2. (Web only) There is currently no way to select specific fields to return in the query. As such, all current queries request all available data from EveryoneAPI. This will be added in an upcoming release. The command-line tool, cnam.php, is not affected by this.

## Credits
Concept and original codebase: Corey Edwards ([@cedwardsmedia](https://www.twitter.com/cedwardsmedia))

Optimization and Debugging: Brian Seymour ([@eBrian](http://bri.io))

## License
_CNAM_ is licensed under the **MIT License**. See LICENSE for more.

---
**Disclaimer**: _CNAM_ is not endorsed by, sponsored by, or otherwise associated with [OpenCNAM](http://www.opencnam.com), [EveryoneAPI](http://www.everyoneapi.com), or [Telo USA, Inc](http://www.telo.com).
