# Enterprise Installation

## Prerequisites

1. A machine running Ubuntu 20.04.
2. A docker password, provided when you signed up.

## Installation (with Internet access)

Run the following in a terminal:
```
curl -O https://perceptilabs.blob.core.windows.net/enterprise/latest/install_perceptilabs_enterprise
chmod +x install_perceptilabs_enterprise
```

If the server already has up-to-date drivers installed 
```
./install_perceptilabs_enterprise --drivers skip
```

Otherwise,
```
./install_perceptilabs_enterprise
```

## Offline Installation
### Prerequisites:
1. NVIDIA GPU drivers version 450 or newer (optional. Required for GPU support)
2. Docker version 20 or newer
3. Docker-compose
4. [NVIDIA container toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html) (optional. Required for GPU support)
5. Perceptilabs offline installation zip you received from us.


### Steps
1. Install prerequisites
2. Unzip the perceptilabs installation zip on the server. It will unpack the following files:
    1. **install_perceptilabs_enterprise** - The installer script you will use.
    1. **system_migrations.zip** - Scripts that the installer uses to migrate existing installations to the newest version
    1. **images.tar** - The docker images that will be loaded and run.
3. Make the installer executable: `chmod +x install_perceptilabs_enterprise`
4. Run the installation script:
```
sudo ./install_perceptilabs_enterprise --airgapped images.tar
```
