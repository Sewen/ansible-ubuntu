# Ansible Ubuntu setup
Ansible roles to setup Ubuntu desktop and Ubuntu server (14.04 and 16.04). This playbook is focused on quickly deploying a "ready to use" dev machine.


## Requirements
- Git
- Ansible 2+ (automatically installed from [Ansible offical PPA](https://launchpad.net/~ansible/+archive/ubuntu/ansible) with the provided install.sh script)


## Installation
First, you need to install Git and Ansible :
```
sudo apt-get install git
git clone https://github.com/Benoth/ansible-ubuntu.git
cd ansible-ubuntu
./install.sh
```

Then you need to customize the playbook `ansible-desktop.yml` (or create a new one) to suit your needs. Every roles are disabled by default.

Run `ansible-playbook ansible-desktop.yml --ask-become-pass` and enter your sudo password to run the playbook

## Roles included

| Role                     | Description                                                                                                                                                                                                                                                                                                                           |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| | **General** |
| common                   | Install a lot of usefull packages (curl, htop, less, zip ... see [corresponding task file](https://github.com/Benoth/ansible-ubuntu/blob/master/roles/common/tasks/main.yml))                                                                                                                                                         |
| locales                  | Configure system locales and timezone                                                                                                                                                                                                                                                                                                 |
| java-openjdk             | Install Default Java JDK                                                                                                                                                                                                                                                                                                              |
| sift                     | Install [Sift](https://sift-tool.org/) tool, a fast and powerful alternative to grep                                                                                                                                                                                                                                                  |
| zsh                      | Install [ZSH](http://www.zsh.org/) and create a [zshrc file](https://github.com/Benoth/ansible-ubuntu/blob/master/roles/zsh/files/zshrc) for the current user / root                                                                                                                                                                  |
| | **Desktop tools** |
| adapta-theme             | Install [Adapta Theme](https://github.com/tista500/Adapta/) from source and apply some gsettings                                                         |
| albert                   | Install [Albert](https://github.com/ManuelSchneid3r/albert) omnilauncher from [Alin Andrei WebUpd8 PPA](https://launchpad.net/~nilarimogard/+archive/ubuntu/webupd8)                                                                                                                                                                  |
| altyo                    | Install [AltYo](https://github.com/linvinus/AltYo) Gtk3 drop-down terminal emulator from [Denis Konstantinov AltYo PPA](https://launchpad.net/~linvinus/+archive/ubuntu/altyo)                                                                                                                                                        |
| arc-theme                | Install [Arc Theme](https://github.com/horst3180/arc-theme) from source and apply some gsettings                                                         |
| atom                     | Install [Atom](https://atom.io/) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/atom) and [Sync Settings](https://atom.io/packages/sync-settings) plugin                                                                                                                                                       |
| chromium                 | Install [Chromium](https://www.chromium.org/). May also install plugins and set policies                                                                                                                                                                                                                                              |
| claws-mail               | Install [Claws Mail](http://www.claws-mail.org/) from [Claws Mail PPA](https://launchpad.net/~claws-mail/+archive/ubuntu/ppa) (14.04)                                                                                                                                                                                                 |
| compton                  | Install [Compton](https://github.com/chjj/compton) lightweight compositor                                                                                                                                                                                                                                                             |
| dbeaver                  | Install [DBeaver](http://dbeaver.jkiss.org/) from online deb file                                                                                                                                                                                                                                                                     |
| desktop                  | Install a lot of usefull packages (meld, tilda, vlc, xclip)                                                                                                                                                                                                                                                                           |
| desktop-cleanup          | Remove Unity sh... integrations and install Nautilus plugins                                                                                                                                                                                                                                                                          |
| desktop-autostart        | Update autostart handling (unhide all apps, create, remove...)                                                                                                                                                                                                                                                                        |
| desktop-preferences-unity | This one is very personal. Imports all my Unity preferences                                                                                                                                                                                                                                                                           |
| filezilla                | Install [Filezilla](https://filezilla-project.org/) (no particular settings, basic installation)                                                                                                                                                                                                                                      |
| firefox                  | Install [Firefox](https://www.mozilla.org/firefox/) (no particular settings, basic installation)                                                                                                                                                                                                                                      |
| flatabulous              | Install [Flatabulous Theme](https://github.com/anmoljagetia/Flatabulous) from source and apply some gsettings                                            |
| geary                    | Install [Geary](https://wiki.gnome.org/Apps/Geary) email client (from [Yorba PPA](https://launchpad.net/~yorba/+archive/ubuntu/ppa) on 14.04)                                                                                                                                                                                         |
| gimp                     | Install [Gimp](https://www.gimp.org/) and some minor settings                                                                                                                                                                                                                                                                         |
| grub-customizer          | Install Grub Customizer using [Daniel Richter PPA](https://launchpad.net/~danielrichter2007/+archive/ubuntu/grub-customizer)                                                                                                                                                                                                          |
| indicator-sysmonitor     | Install [indicator-sysmonitor](https://github.com/fossfreedom/indicator-sysmonitor) from [FOSSFreedom PPA](https://launchpad.net/~fossfreedom/+archive/ubuntu/indicator-sysmonitor)                                                                                                                                                   |
| ksuperkey                | Install [ksuperkey](https://github.com/hanschen/ksuperkey) using [Eugene Mikhantiev PPA](https://launchpad.net/~mehanik/+archive/ubuntu/ksuperkey)                                                                                                                                                                                    |
| libreoffice              | Install [LibreOffice](https://www.libreoffice.org/) using [LibreOffice 5.1 PPA](https://launchpad.net/~libreoffice/+archive/ubuntu/libreoffice-5-1)                                                                                                                                                                                   |
| min                      | Install [Min browser](https://minbrowser.github.io/min/) from online deb file                                                                                                                                                                                                                                                         |
| mysql-workbench          | Install [MySQL WorkBench](https://www.mysql.fr/products/workbench/) from online deb file                                                                                                                                                                                                                                              |
| nautilus-plugins         | Install Nautilus plugins                                                                                                                                                                                                                                                                                                              |
| nemo                     | Install [Nemo](https://github.com/linuxmint/nemo) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/nemo)                                                                                                                                                                                                         |
| notepadqq                | Install [Notepadqq](http://notepadqq.altervista.org/wp/) from [Notepadqq Team PPA](https://launchpad.net/~notepadqq-team/+archive/ubuntu/notepadqq)                                                                                                                                                                                   |
| notify-osd               | Install ehanced Notidy-OSD from [Leolik PPA](https://launchpad.net/~leolik/+archive/ubuntu/leolik)                                                                                                                                                                                                                                    |
| qutebrowser              | Install [qutebrowser](https://qutebrowser.org/) from online deb file                                                                                                                                                                                                                                                                  |
| remarkable               | Install [Remarkable](https://remarkableapp.github.io/linux.html) from online deb file                                                                                                                                                                                                                                                 |
| remmina                  | Install [Remmina](http://www.remmina.org/)                                                                                                                                                                                                                                                                                            |
| shutter                  | Install [Shutter](http://shutter-project.org/) screenshot tool                                                                                                                                                                                                                                                                        |
| skype                    | Install [Skype](https://www.skype.com/)                                                                                                                                                                                                                                                                                               |
| smartgit                 | Install [SmartGit](http://www.syntevo.com/smartgit/) from [Eugene San PPA](https://launchpad.net/~eugenesan/+archive/ubuntu/ppa)                                                                                                                                                                                                      |
| sublime3                 | Install [Sublime Text 3](https://www.sublimetext.com/3) from [WebUpd8 PPA](https://launchpad.net/~webupd8team/+archive/ubuntu/sublime-text-3) and the [Package Control](https://packagecontrol.io/) plugin                                                                                                                            |
| sunflower                | Install [SunFlower](http://sunflower-fm.org/download)fom online dev                                                                                                                                                                                                                                                                   |
| teamviewer               | Install [TeamViewer](https://www.teamviewer.com/) from online deb file                                                                                                                                                                                                                                                                |
| thunderbird              | Install [Thunderbird](https://www.mozilla.org/thunderbird/) (no particular settings, basic installation)                                                                                                                                                                                                                              |
| vagrant                  | Install [Vagrant](https://www.vagrantup.com/) from online deb file                                                                                                                                                                                                                                                                    |
| ultra-flat-icons         | Install [Ultra flat icons](http://www.noobslab.com/2015/01/make-linux-more-elegant-with-ultra-flat.html) from [Noobslab PPA](https://launchpad.net/~noobslab/+archive/ubuntu/icons)                                                                                                                                                   |
| virtualbox               | Install [VirtualBox](https://www.virtualbox.org/) from VirtualBox APT repositories                                                                                                                                                                                                                                                    |
| vokoscreen               | Install [Vokoscreen](http://www.kohaupt-online.de/hp/) screencast tool                                                                                                                                                                                                                                                                |
| wine                     | Install [Wine](https://www.winehq.org/) from [Ubuntu Wine Team PPA](https://launchpad.net/~ubuntu-wine/+archive/ubuntu/ppa) and create [HeidiSQL](http://www.heidisql.com/) shortcut                                                                                                                                                  |
| workrave                 | Install [Workrave](http://www.workrave.org/) a tool  assists in the recovery and prevention of Repetitive Strain Injury (RSI)                                                                                                                                                                                                         |
| xfce-dockbarx            | Install [DockbarX](https://github.com/M7S/dockbarx) and the XFCE plugin from [Dockbar main PPA](https://launchpad.net/~dockbar-main/+archive/ubuntu/ppa)                                                                                                                                                                              |
| xmind                    | Install [XMind](http://www.xmind.net/) from online deb file                                                                                                                                                                                                                                                                           |
| | **Dev tools** |
| blackfire                | Install [Blackfire](https://blackfire.io/) from Blackfire deb repository                                                                                                                                                                                                                                                              |
| bower                    | Install [Bower](https://bower.io/) as a global package using NPM                                                                                                                                                                                                                                                                      |
| browsersync              | Install [Browsersync](https://www.browsersync.io/) as a global package using NPM                                                                                                                                                                                                                                                      |
| composer                 | Install [Composer](https://getcomposer.org/), PHP Dependency Manager                                                                                                                                                                                                                                                                  |
| gulp                     | Install [Gulp](http://gulpjs.com/) as a global package using NPM                                                                                                                                                                                                                                                                      |
| mailcatcher              | Install [Mailcatcher](https://mailcatcher.me/) as a service                                                                                                                                                                                                                                                                           |
| mailhog                  | Install [MailHog](https://github.com/mailhog/MailHog) (Catches SMTP emails, like MailCatcher) as a service                                                                                                                                                                                                                            |
| php-phar-tools           | Install common PHP tools (PHPUnit, Codeception, PHP-CS-Fixer, ...)                                                                                                                                                                                                                                                                    |
| webpack                  | Install [webpack](https://webpack.github.io/docs/) as a global package using NPM                                                                                                                                                                                                                                                      |
| | **Services & server tools** |
| apache2                  | Install [Apache 2 HTTP Server](https://httpd.apache.org/) with some admin tools and remove defaults hosts                                                                                                                                                                                                                             |
| apache2-php              | Basic Apache 2 PHP Virtualhosts creation (you may need to run the "php" role first, depending on your configuration)                                                                                                                                                                                                                  |
| beanstalkd               | Install [beanstalkd](http://kr.github.io/beanstalkd/) with default configuration                                                                                                                                                                                                                                                      |
| docker                   | Install [Docker](https://www.docker.com/) and Docker compose from Docker deb repository                                                                                                                                                                                                                                               |
| elasticsearch            | Install [Elasticsearch](http://elastic.co/) from Elastic deb repository                                                                                                                                                                                                                                                               |
| exim                     | Install [Exim](http://www.exim.org/) and disable local delivery                                                                                                                                                                                                                                                                       |
| fail2ban                 | Install [Fail2ban](http://www.fail2ban.org/) with default config                                                                                                                                                                                                                                                                      |
| hhvm                     | Install [HHVM](http://hhvm.com/) from HHVM deb repository                                                                                                                                                                                                                                                                             |
| memcached                | Install [Memcached](https://memcached.org/) with default config                                                                                                                                                                                                                                                                       |
| mysql56                  | Install [MySQL 5.6](http://www.mysql.com/) (using 14.04 repositories on 16.04)                                                                                                                                                                                                                                                        |
| mysql57                  | Install [MySQL 5.7](http://www.mysql.com/) **Only available on Ubuntu 16.04+**                                                                                                                                                                                                                                                        |
| nginx                    | Install [nginx](https://nginx.org/) and remove defaults hosts                                                                                                                                                                                                                                                                         |
| nginx-php-fpm            | Basic nginx PHP-FPM Virtualhosts creation (you may need to run the "php" role first, depending on your configuration)                                                                                                                                                                                                                 |
| nodejs                   | Install [NodeJS](https://nodejs.org/en/) from Node deb repository                                                                                                                                                                                                                                                                     |
| phantomjs                | Install [PhantomJS](http://phantomjs.org/)                                                                                                                                                                                                                                                                                            |
| php                      | Co-Install [PHP 5.6 and 7.0](http://php.net/) from [Ondřej Surý PPA](https://launchpad.net/~ondrej/+archive/ubuntu/php), with the "standard" set of extensions and settings                                                                                                                                                           |
| php-pecl                 | Install PHP PECL extensions                                                                                                                                                                                                                                                                                                           |
| python                   | Install [Python](https://www.python.org/)                                                                                                                                                                                                                                                                                             |
| redis                    | Install [Redis](http://redis.io/)                                                                                                                                                                                                                                                                                                     |
| ruby                     | Install [Ruby](https://www.ruby-lang.org/) from [Brightbox PPA](https://launchpad.net/~brightbox/+archive/ubuntu/ruby-ng)                                                                                                                                                                                                             |
| ssh                      | Install [OpenSSH Server](http://www.openssh.com/)                                                                                                                                                                                                                                                                                     |
| | **Others** |
| dotfiles                 | Clone my personal [dotfiles](https://github.com/Benoth/dotfiles) Git repository and their dependencies                                                                                                                                                                                                                                |
| projects-installer       | Clone my repository [projects-installer](https://github.com/Benoth/projects-installer), used to deploy my personal and clients projects (Ansible based)                                                                                                                                                                               |
