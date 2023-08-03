### TPC DS Unix Compiled Version

## Setup

### Linux

Make sure the required development tools are installed:

Ubuntu:

```
sudo apt-get install gcc make flex bison byacc git
```

CentOS/RHEL:

```
sudo yum install gcc make flex bison byacc git
```

Then run the following commands to clone the repo and build the tools:

```
cd tools
make CC=gcc-9 OS=LINUX
```

### macOS

Make sure the required development tools are installed:

```
xcode-select --install
```

Then run the following commands to clone the repo and build the tools:

```
cd tools
make OS=MACOS
```

## Using the TPC-DS tools

### Data generation

* Data generation is done via `dsdgen`.
* Run `dsdgen -help` for all options.

### Query generation

* Query generation is done via `dsqgen`.
* Run `dsqgen -help` for all options.

Below command will generate all 99 queries in numerical order (`-QUALIFY`) for the 10TB scale factor (`-SCALE`) using the Netezza dialect template (`-DIALECT`) with the output going to `/tmp/query_0.sql` (`-OUTPUT_DIR`).

```
dsqgen \
-DIRECTORY ../query_templates \
-INPUT ../query_templates/templates.lst \
-VERBOSE Y \
-QUALIFY Y \
-SCALE 10000 \
-DIALECT netezza \
-OUTPUT_DIR /tmp
```
