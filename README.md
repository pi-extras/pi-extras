# Pi Extras
## Introduction
Pi Extras is an APT repository with extra packages for Raspberry Pi. Automatic update scripts are running in the background, providing latest software to users.

The purpose of its establishment is to make up for the software ecology of the Raspberry Pi. And it is also an alternative to [Raspbian Addons](https://github.com/raspbian-addons) which has been abandoned by its maintainer.

# Installation
1. Install the dependencies before adding the Pi Extras.
```
sudo apt update && sudo apt install -y gnupg apt-transport-https
```
2. Add Pi Extras's public GPG key to the apt sources keyring.
```
curl -fsSL https://apt.pi-extras.ml/KEY.gpg | sudo gpg --dearmor -o /usr/share/keyrings/pi-extras-archive-keyring.gpg
```
3. Create the package list for Pi Extras.
```
echo "deb [signed-by=/usr/share/keyrings/pi-extras-archive-keyring.gpg] http://apt.pi-extras.ml/debian extras main" | sudo tee /etc/apt/sources.list.d/pi-extras.list
```
4. Refresh the apt configuration.
```
sudo apt update
```

Now you can install packages from the repo via `sudo apt install PACKAGE_NAME`.

(Replace `PACKAGE_NAME` with the name of the package you want to install)

The full list of the packages can be found [here](https://apt.pi-extras.ml/debian/pool/main/).

## To-do
- [ ] Create auto-update scripts
- [ ] Add multiple mirrors of the repo
- [ ] Create a script to add or remove the repo
