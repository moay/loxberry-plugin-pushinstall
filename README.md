# loxberry-plugin-pushinstall

Adds instant plugin installation via ssh.

### Installation

Install the package with composer:

```
composer require moay/loxberry-plugin-pushinstall --dev
```

### Usage

In order to push your current dev status to your LoxBerry, go to your plugin dev folder an run

```
./vendor/bin/pushinstall
```

### Speeding up the process

By default, you will have to enter your ssh password on every publish. This can be bypassed by using
ssh keys as authentication mechanism. In order to create an ssh key and enable its use as password
replacement during plugin publication via ssh, run

```
./vendor/bin/pushinstall-enable-ssh-key
```

Have fun. 

### System requirements

Tested on Mac, should run on Linux. Won't run on Windows.
