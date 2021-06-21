# UpdateMe and Erase-Install
Some stuff to facilitate macOS major update or full erase and reinstall for non-admin users.

## Prerequises
* __A working Munki installation is required.__ More infos [here](https://github.com/munki/munki)
* __Hello-IT functionals parameters with the key _allow subdomains_ to true are mandatory.__ See Wiki [here](https://github.com/ygini/Hello-IT/wiki/Preferences-subdomain)
* Latest release for erase-install.sh file can be found [here](https://github.com/grahampugh/erase-install/releases)

## Usage & Tips
You can make two files with [Packages](http://s.sudre.free.fr/Software/Packages/about.html) to split these functions in two items for Munki (Erase&Install must be optional). <br/>The IT folder can be relocated, but beware of the folder access confidential limitation and change ITFOLDER variable in both post-install scripts. <br/>__Warning ! Theses tools can easily destroy all data on your computer, please test them and understand how it's work before use.__

## Packages content

### Major Update package need these files :
* /etc/sudoers.d/com-github-darkomen78-majorupdate-sudoers
* /Users/Shared/IT/update/com.github.ygini.Hello-IT.MajorUpdate.plist
* /Users/Shared/IT/erase/erase-install.sh  
* /Library/Application Support/com.github.ygini.hello-it/CustomScripts/com.github.darkomen78.hello-it.major-update.sh
* As a post-install script : /scripts/postinstall_majorupdate

### Erase & Install package need these files :
* /etc/sudoers.d/com-github-darkomen78-eraseinstall-sudoers
* /Users/Shared/IT/erase/com.github.ygini.Hello-IT.Erase
* /Users/Shared/IT/erase/erase-install.sh
* /Library/Application Support/com.github.ygini.hello-it/CustomScripts/com.github.darkomen78.hello-it.eraseall.sh  
* As a post-install script : /scripts/postinstall_erase  
_Optional_ : you can add some .pkg files in /Users/Shared/IT/erase/pkg/ folder for auto-installation after the macOS reinstallation.