# Knife Solo Data Bag
A knife plugin to make working with data bags easier in a chef solo environment

## Build Status
![Build Status](https://secure.travis-ci.org/thbishop/knife-solo_data_bag.png)

## Installation

    gem install knife-solo_data_bag

## Usage

### Create
Create a plain text data bag

    $ knife solo data bag create apps app_1

Create an encrypted data bag with the provided string as the secret

    $ knife solo data bag create apps app_1 -s secret_key

Create an encrypted data bag with the provided file content as the secret

    $ knife solo data bag create apps app_1 --secret-file 'SECRET_FILE'

Create a data bag item with JSON from the command line (works with encryption)

    $ knife solo data bag create apps app_1 --json '{"id": "app_1", "username": "bob"}'

### Edit
Edit a plain text data bag

    $ knife solo data bag edit apps app_1

Edit an encrypted data bag with the provided string as the secret

    $ knife solo data bag edit apps app_1 -s secret_key

Edit an encrypted data bag with the provided file content as the secret

    $ knife solo data bag edit apps app_1 --secret-file 'SECRET_FILE'

### List
List all of the data bag

    $ knife solo data bag list

### Show
Show the plain text content of a data bag (if this is an encrypted data bag, it will return the encrypted data)

    $ knife solo data bag show apps app_1

Show the unencrypted content of an encrypted data bag with the provided string as the secret

    $ knife solo data bag show apps app_1 -s secret_key

Show the unencrypted content of an encrypted data bag with the provided file content as the secret

    $ knife solo data bag show apps app_1 --secret-file 'SECRET_FILE'

You can also display any of the above variations in JSON format with `-F json`

    $ knife solo data bag show apps app_1 -s secret_key -F json

## Notes
This plugin will rely on the configured data_bag_path for placement of the data
bags.  This defaults to '/var/chef/data_bags', but can be overriden in your chef
client config.

## Version Support
This plugin has been tested on the following:

Chef:
* 0.10.10
* 10.12.0

Ruby:
* 1.9.2
* 1.9.3

OS:
* OSX
* Linux

## Contribute
* Fork the project
* Make your feature addition or bug fix (with tests and docs) in a topic branch
* Bonus points for not mucking with the gemspec or version
* Send a pull request

## License
See LICENSE for details
