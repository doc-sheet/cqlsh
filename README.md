[![PyPI version](https://badge.fury.io/py/cqlsh.svg)](https://badge.fury.io/py/cqlsh)
![PyPI - Python Version](https://img.shields.io/pypi/pyversions/cqlsh)
[![Downloads](https://pepy.tech/badge/cqlsh)](https://pepy.tech/project/cqlsh)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

# `cqlsh`

`cqlsh` is a Python-based command-line client for running `CQL` commands on a `cassandra` cluster.

Normally it's packaged as part of the full Apache Cassandra™ installation. This repo repackages it into a standalone Python package for lighter-weight installs.

### Installing:

Install and update using [`pip`](https://pip.pypa.io/en/stable/quickstart/):
```
$ pip install -U cqlsh
```

### Running:

```
$ cqlsh --help
```

### Documentation:

Documentation is available as part of the official [Apache Cassandra™ documentation](https://cassandra.apache.org/doc/latest/cassandra/managing/tools/cqlsh.html).

### Contributing:

Because this is a repackaging of `cqlsh` from the official [Cassandra repo](https://gitbox.apache.org/repos/asf/cassandra.git), **only issues / PRs related to PyPI packaging should be opened against this repo**. If you would like to contribute to `cqlsh` itself, [find out more information here](https://github.com/apache/cassandra/blob/trunk/CONTRIBUTING.md).

Steps to sanity check that the packaging works as expected:

1. Install `cqlsh` locally (probably in a `virtualenv`):
```
$ pip install -e .  # run from within the cqlsh directory
```
2. Start a local copy of Cassandra:
```
$ docker pull cassandra
$ docker run -it --rm -p 9042:9042 cassandra
```
3. Verify `cqlsh` successfully connects to the server:
```
$ cqlsh

Connected to Test Cluster at 127.0.0.1:9042
[cqlsh 6.1.0 | Cassandra 4.1.0 | CQL spec 3.4.5 | Native protocol v5]
Use HELP for help.
cqlsh>
```

This PyPI package is maintained by [Jeff Widman](https://github.com/jeffwidman) and [Brad Schoening](https://github.com/bschoening). Previous maintainers: [Spiro](https://github.com/spiside) and [Andrew Mussey](https://github.com/amussey).


### Changelog:

Unfortunately the Cassandra project does not always increment the `cqlsh` version number, so for every
release we need to document not only the `cqlsh` version but also the `cassandra` version in which it
shipped.

#### 6.2.0 (September 16, 2024)

This packages `cqlsh` `6.2.0` from [Cassandra 5.0.0](https://github.com/apache/cassandra/blob/cassandra-5.0.0/pylib/cqlshlib):
 * Add HISTORY command for CQLSH (CASSANDRA-15046)
 * Add CQLSH command SHOW REPLICAS (CASSANDRA-17577)
 * Cassandra 5.0 has refactored all cqlsh logic to be in cqlshlib, with the new cqlshmain.py replacing behavior formerly in bin/cqlsh.py
 * Replace 'wcwidth.py' with pypi module (CASSANDRA-17287)

#### 6.1.3 (Feburary 23, 2023)

This packages `cqlsh` `6.1.0` from [Cassandra 4.1.4](https://github.com/apache/cassandra/blob/cassandra-4.1.4/bin/cqlsh.py):
 * CQLSH emits a warning when the server version doesn't match (CASSANDRA-18745)
 * Fix CQLSH online help topic link (CASSANDRA-17534)

#### 6.1.2 (March 24, 2023)

This packages `cqlsh` `6.1.0` from [Cassandra 4.1.1](https://github.com/apache/cassandra/blob/cassandra-4.1.1/bin/cqlsh.py):
* Now supports Python 3.11.
* Although this is pulled from a Cassandra `4.x` release, it is protocol compatible with Cassandra `3.x` clusters, with the exception of `DESCRIBE` keywords which require a 4.x cluster.

#### 6.1.1 (skipped due to a versioning issue)

#### 6.1.0 (Jan 4, 2023)

This packages `cqlsh` `6.1.0` from [Cassandra 4.1](https://github.com/apache/cassandra/blob/cassandra-4.1.0/bin/cqlsh.py):
* Requires Python 3.6+.
* Although this is pulled from a Cassandra `4.x` release, it is protocol compatible with Cassandra `3.x` clusters, with the exception of `DESCRIBE` keywords which require a 4.x cluster.

#### 6.0.1 (Jan 18, 2022)

The actual source code is identical to the `cqlsh` `6.0.0` release, except it's now packaged as
a module. This allows it to be used as a library, not just an executable script. It also provides
better Windows support. Details in https://github.com/jeffwidman/cqlsh/pull/7 by @bschoening.

Note: This release was yanked from PyPI because it [broke Python 2 compatibility](https://github.com/jeffwidman/cqlsh/issues/11).

#### 6.0.0 (Aug 3, 2021)

This packages `cqlsh` `6.0.0` from [Cassandra 4.0](https://github.com/apache/cassandra/blob/cassandra-4.0.0/bin/cqlsh.py):
* Requires Python 3.6+ or 2.7 (although support for Python 2 is deprecated).
* Although this is pulled from a Cassandra `4.x` release, it should generally work against Cassandra `3.x` clusters without needing to set any flags.


#### 6.0.0b4 (Mar 9, 2021)

This packages `cqlsh` `5.0.1` from [Cassandra 4.0-beta4](https://github.com/apache/cassandra/blob/cassandra-4.0-beta4/bin/cqlsh.py):
* Now supports Python 3.
* Although this is pulled from a Cassandra `4.x` release, it should generally work against Cassandra `3.x` clusters without needing to set any flags.

#### 5.0.5 (Mar 9, 2021)

This packages `cqlsh` `5.0.1` from [Cassandra 3.11.10](https://github.com/apache/cassandra/blob/cassandra-3.11.10/bin/cqlsh.py).

#### 5.0.4 (Mar 29, 2017)

This packages `cqlsh` `5.0.1` from [Cassandra 3.4.0](https://github.com/apache/cassandra/blob/cassandra-3.4/bin/cqlsh.py).


#### 5.0.3 (Mar 21, 2016)

This packages `cqlsh` `5.0.1` from [Cassandra 2.2.0](https://github.com/apache/cassandra/blob/cassandra-2.2.0/bin/cqlsh.py).


#### 4.1.1 (Feb 11, 2014)

This packages `cqlsh` `4.1.1` from [Cassandra 2.0.5](https://github.com/apache/cassandra/blob/cassandra-2.0.5/bin/cqlsh).


#### 4.1.0 (Dec 2, 2013)

This packages `cqlsh` `4.1.0` from [Cassandra 2.0.3](https://github.com/apache/cassandra/blob/cassandra-2.0.3/bin/cqlsh).


#### 4.0.1 (Oct 14, 2013)

This packages `cqlsh` `4.0.1` from [Cassandra 2.0.1](https://github.com/apache/cassandra/blob/cassandra-2.0.1/bin/cqlsh).
