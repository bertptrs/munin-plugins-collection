# Additional Munin plugins

This repository contains my personally curated and somewhat biased
selection of high-quality user-created Munin plugins.


## Motivation

The [munin/contrib](https://github.com/munin-monitoring/contrib) repo is
a wonderful source of munin plugins, but the quality is widely varying
and things aren't documented that well.

While that's inherent to a user contributed repository, it leaves me
wanting for a more extended version of the core plugins. This is where
this repository comes in.

I found myself writing quite a few one-off munin plugins of poor
quality, so I decided to clean them up and bundle them in a single
package.

## Plugins

See below for a brief description of the plugins, in alphabetic order.
More detailed descriptions are available in the specific plugins
themselves.

### milter\_greylist

Monitor the number of whitelisted/greylisted tuples for the
milter-greylist plugin for postfix.

Possibly needs to run as postfix in order to read the greylist database.
Tested on Ubuntu 14.04 and 16.06.

### pacman

Monitor the number of updates pending, with warnings for updates.

### rpi\_cputemp

CPU temperature measuring for the Raspberry Pi using the Raspberry Pi
firmware. Tested with a Raspberry Pi 2b.

### systemd\_services

Monitor a specific set of systemd plugins, and send warnings on failure.

Use the `env.services` directive to specify plugins to send warnings
for, and use `env.critical_services` to specify plugins to send critical
warnings for.

## Contributing

Feel free to send a pull request with a plugin that would fit in here.
For your contribution to be considered, try to make sure that

- the plugin is written in a fast scripting language (noone like the jvm
  startup times)
- you specify a meaningful `autoconf` operation
- you don't require configuration outside the munin plugin configuration
- you don't have any dependencies not already present by default on a
  system running that which you are trying to monitor
- the plugin submitted is not already present in the `munin-node`
  package of the major distros (Centos, Ubuntu, Debian, Arch Linux)

That last one is important, as most Linux distributions already include
some of the better `contrib` plugins since the core plugins are somewhat
limited.

## License

The source code is available under the MIT license. That means you can
do pretty much anything, as long as you give me credit
