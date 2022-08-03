# LibreLens (an OpenLens fork)

This repository is a direct fork of the famous [OpenLens](https://github.com/lensapp/lens) project that includes binary builds for every stable or release version.

### Why is a fork necessary?

As of today, Mirantis, the main developers behind Lens only release a [propritary version of Lens](https://k8slens.dev/) on their Website. While LibreLens can not provide any nameful support, it still offers many advantages compared to the Mirantis business solution:

- The propritary version [requires LensID](https://github.com/lensapp/lens/issues/5444) and your agreement to their Terms of Service. This open source build is MIT licensed and allows you to do with it whatever you want.
- The propritary version adds additional features that you may want to have, especially if collaborating with a team. This open source build does only include the features that are not also included in this repository.
- The proprietary version follows a subscription model that allows Mirantis to support your exact needs. This open source build provides you with a tool and that's it. No business support, no cost, no terms of service.

# Install Lens
- go to the [releases page](https://github.com/LibreLens/lens/releases)
- download the binary for your system and use your default install procedure.

Packages are not code signed which may be a problem on Windows or Mac computers if you are not able to elevate priviledges. For code signed packages, a mac/windows developer account is neccessary. If you are able to provide the necessary resources for code signing, please let me know in the respective issue for [windows](https://github.com/LibreLens/lens/issues/9) or [mac](https://github.com/LibreLens/lens/issues/5)


# Build Lens on your own system

the following instructions are heavily inspired by github user [jslay88](https://github.com/lensapp/lens/issues/5444#issuecomment-1140483224)

### Mac
##### Install Dependencies
- [homebrew requirements](https://docs.brew.sh/Installation#macos-requirements)
- [homebrew](https://github.com/Homebrew/install)
- git, make via brew: `brew install git make`
- [nvm](https://github.com/nvm-sh/nvm#installing-and-updating)
##### Build and Install LibreLens
```bash
# set up node 14 and yarn
nvm install 14
nvm use 14
npm install -g yarn

# build LibreLens
https://github.com/LibreLens/lens.git
cd lens
make build

# install LibreLens
cp -Rfp dist/mac/OpenLens.app ~/Applications/
```

### Windows
##### Install Dependencies
- `choco install make visualstudio2019buildtools visualstudio2019-workload-vctools`
- [nvm for windows](https://github.com/coreybutler/nvm-windows#installation--upgrades)
##### Build and Install LibreLens
```bash
# set up node 14 and yarn
nvm install 14
nvm use 14
npm install -g yarn

# build LibreLens
https://github.com/LibreLens/lens.git
cd lens
make build

# install LibreLens
start ./dist/'LibreLens Setup <your-version>.exe'
```

### Debian-based systems
- `sudo apt-get install -y g++ make curl git`
- [nvm](https://github.com/nvm-sh/nvm#installing-and-updating)
##### Install Dependencies
##### Build and Install LibreLens
```bash
# set up node 14 and yarn
nvm install 14
nvm use 14
npm install -g yarn

# build LibreLens
https://github.com/LibreLens/lens.git
cd lens
make build

# install LibreLens
sudo dpkg -i dist/OpenLens-<your-version>.deb
```


# Disclaimer

This software is provided "as is". In no event shall the authors, maintainers and copyright holders be liable for any direct, indirect, incidental, special, exemplary, or consequential damages (including, but not limited to procurement of substitute goods or services; loss of use, data, or profits; or business interruption) however caused and on any theory of liability, whether in contract, strict liability, or tort (including negligence or otherwise) arising in any way out of the use of this software, even if advised of the possibility of such damage.
