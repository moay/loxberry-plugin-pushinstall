# loxberry-plugin-pushinstall

Adds instant plugin installation via ssh.

## Installation

#### Using Composer

Install the package with [composer](https://getcomposer.org/):

```bash
composer require moay/loxberry-plugin-pushinstall --dev
```

#### Without Composer

You could also just download this repo and use the script. Make sure to maintain the directory structure
as the scripts in `/lib` will be called and are needed for execution.

## Usage

In order to push your current dev status to your LoxBerry, go to your plugin dev folder an run

```bash
./vendor/bin/pushinstall
```

### Parameters

In order to speed up the usage, you can pass the LoxBerry SecurePin as a parameter as well as skipping
the connection configuration. Usage could look like this:

```bash
./vendor/bin/pushinstall -s -p 1234
```

Flags:

* `-s` will skip the connection questions if the IP and username of your LoxBerry have been entered at least once
* `-p [securepin]` will set the SecurePin
* `-c` will remove previously stored connection details


### Passwordless ssh connection

By default, you will have to enter your ssh password on every publish. This can be bypassed by using
ssh keys as authentication mechanism. In order to create an ssh key and enable its use as password
replacement during plugin publication via ssh, run

```bash
./vendor/bin/pushinstall-enable-ssh-key
```

This will create a new ssh key for plugin installation (if it doesn't exist yet), add it as IdentityFile to the local ssh configuration (only for 
the specified LoxBerry) and pass the key to your LoxBerry via ssh.

## System requirements

Tested on Mac, should run on Linux. Won't run on Windows.

## Credits

Uses [shFlags](https://github.com/kward/shflags) by Kate Ward. Thanks for that!
