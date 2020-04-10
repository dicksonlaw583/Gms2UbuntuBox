# Ubuntu Build Box for GameMaker Studio 2

## Download

Clone this repository or download from the [Releases Page](https://www.github.com/dicksonlaw583/Gms2UbuntuBox/releases).

## Requirements

*Note:* You must have administrative privileges on your system to set up this box.

- Windows 10 or Mac OS X 10.14+ (Mojave or higher)
- [VirtualBox](https://www.virtualbox.org) (6.0.x or higher)
- [Vagrant](https://www.vagrantup.com) (2.2.6 or higher)
  - Requires [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest) (to install: `vagrant plugin install vagrant-vbguest`)
- [GameMaker Studio 2](https://www.yoyogames.com/get) (2.2.x or higher)

## Starting the Box

Simply double-click `start.bat` on Windows or `start.command` on Mac OS X. You can also `cd` to the download directory and run `vagrant up`.

*Note:* When the box starts up for the first time, it will attempt to create a new host-only network. Please accept all firewall and UAC/Gatekeeper warnings related to this.

## GameMaker Studio 2 Configurations

Go to the Target dropdown, select Ubuntu, then click the pencil next to the Device Column. Click "Add New Device" and fill in the following details:

- Display Name: `GMS 2 Build Box`
- Host Name: `192.168.222.222`
- User Name: `vagrant`
- Password: `vagrant`
- Install Folder: `/builds`

Verify your setup by clicking Test Connection.
