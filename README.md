![GitHub release (latest by date)](https://img.shields.io/github/v/release/CoffeePerry/dynu-renew)
![PyPI](https://img.shields.io/pypi/v/dynu-renew?logo=PyPI&logoColor=white)
![PyPI - Status](https://img.shields.io/pypi/status/dynu-renew)

![PyPI - Python Version](https://img.shields.io/pypi/pyversions/dynu-renew?logo=Python&logoColor=white)
![PyPI - Implementation](https://img.shields.io/pypi/implementation/dynu-renew)

[![GitHub license](https://img.shields.io/github/license/CoffeePerry/dynu-renew)](https://github.com/CoffeePerry/dynu-renew/blob/master/LICENSE)

[![GitHub issues](https://img.shields.io/github/issues/CoffeePerry/dynu-renew)](https://github.com/CoffeePerry/dynu-renew/issues)

# dynu-renew

A Python module to renew public IP address associated with a *Dynu* domain.

This Python module, through the "_renew_domains_ip_" function, retrieves the current public IP address, stores it in a local _SQLite_ database, and communicates it to _Dynu_.

## Quick Start

First you need to download the "_dynu-renew_" package, for example via _pip_:

```
pip install dynu-renew
```

At this point you need to create the "_instance_" folder:

```
mkdir instance
```

And create the "_config.py_" file inside, taking inspiration from what you can find inside the "_configs_" folder of this repo.

In the "_DYNU_PASSWORD_" field I recommend you enter the _Dynu IP Update Password_ instead of the Dynu account access password, because the _Dynu IP Update Password_ has limited privileges.

Finally, to start it via _CLI_ simply send the command:

```
python -m dynu_renew
```

If the output is empty, then the IP renewal was successful, otherwise the error received from the _Dynu_ API is returned.

I recommend you add scheduled execution of _dynu-renew_ by adding it to the _crontab_, as follows:

```
crontab -e
```

Then inserting a new line like this:

```
*/5 * * * * python -m dynu_renew >> ~/dynu_renew.log 2>&1
```
