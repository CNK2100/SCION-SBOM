# SCION-SBOM

The implementation of RBOM into SCION infrastructure.
The code is based on [the SCION implementation](https://github.com/netsec-ethz/scion).

## Installation

Installation packages for Debian and derivatives are available for x86-64, arm64, x86-32 and arm.
These packages can be found in the [latest release](https://github.com/scionproto/scion/releases/latest).
Packages for in-development versions can be found from the [latest nightly build](https://buildkite.com/scionproto/scion-nightly/builds/latest).

Alternatively, "naked" pre-built binaries are available for Linux x86-64 and
can be downloaded from the [latest release](https://github.com/scionproto/scion/releases/latest) or the
[latest nightly build](https://buildkite.com/scionproto/scion-nightly/builds/latest).

### Building on Ubuntu environment

Use the [documentation site](https://docs.scion.org/en/latest/dev/setup.html) for build instructions.\
Below is the environment information used to test building.

- OS: Ubuntu 24.04 VM on VirtualBox
- CPU: 4
- RAM: 8GB
- Disk size: 40GB 

### Errors

- Building SCION on Windows WSL is not recommended. (Remote execution issues)
- Installing Python packages on VM (needs checking)
  - Create Python virtual environment & activate
  - Install following packages: python3-pip, python3-setuptools, python3-wheel
  - May need to use `pip install package_name --break-system-packages`
    

## RBOM Implementation

All modified code is labeled with the phrase _"rbomcode"_.\
Below are the modified files, with some notable functionalities.

pkg/proto/control\_plane/seg\_extensions.pb.go\
pkg/proto/daemon/daemon.pb.go
- Files generated using _.proto_ definitions below. **Do not edit these files!**

proto/control\_plane/v1/seg\_extensions.proto\
proto/daemon/v1/daemon.proto
- _.proto_ files are data schemes where fields are defined.

control/beaconing/staticinfo_config.go\
control/beaconing/staticinfo\_config\_test.go
- Structure of RBOM information is defined in _staticinfo\_config.go_,\
and test values are assigned in _staticinfo\_config\_test.go_.

scion/showpaths/showpaths.go
- Code for returning human readable output.

**Other files:**
- private/path/combinator/staticinfo_accumulator.go
- pkg/private/xtest/graph/graph.go
- pkg/segment/extensions/staticinfo/staticinfo.go
- pkg/snet/path.go
- private/path/combinator/staticinfo_accumulator.go
