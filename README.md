# Documentations

- http://book.open-falcon.org
- http://docs.openfalcon.apiary.io

# Get Started

    git clone https://github.com/Cepave/open-falcon
    cd open-falcon
    git submodule update —-init

# Compilation

```bash
# all modules
make all

# specified module
make agent
```

# Run Open-Falcon Commands

Agent for example:

    ./open-falcon agent [build|pack|start|stop|restart|status|tail]

# Package Management
## How-to

Make sure you're using Go 1.5+ and **GO15VENDOREXPERIMENT=1** env var is exported. (You can ignore GO15VENDOREXPERIMENT using Go 1.6+.)

 0. Install `trash` by `go get github.com/rancher/trash`.
 1. Edit `trash.yml` file to your needs. See the example as follow.
 2. Run `trash --keep` to download the dependencies.

```yaml
package: github.com/Cepave/open-falcon

import:
- package: github.com/Cepave/common              # package name
  version: origin/develop                        # tag, commit, or branch
  repo:    https://github.com/Cepave/common.git  # (optional) git URL
```

# Package Release

	make clean all pack
