# passman - A simple command line password manager

## Features

* Strong encryption via GPG
* Support for either public-key or symmetric encryption
* Add, get and delete passwords with simple commands
* Easy web browser / login forms support
* Custom regular expressions for matching windows

## Usage

### Prerequisites and configuration

1. Make sure you have the following software installed and accessible on your
   system:

   [bash](http://www.gnu.org/software/bash/),
   [gpg2](http://www.gnupg.org/),
   [dmenu](http://tools.suckless.org/dmenu/),
   [xdotool](http://www.semicomplete.com/projects/xdotool/),
   [xvkbd](http://homepage3.nifty.com/tsato/xvkbd/),
   [pwgen](http://sourceforge.net/projects/pwgen/)

   For Debian/Ubuntu users, this translates into having the following packages
   installed: bash, gnupg2, suckless-tools, xdotool, xvkbd and pwgen.

2. Run passman-config. It will set up $HOME/.passman/config for you.

3. For convenience set up a GPG-Agent which caches your GPG credentials for some
   time.

### Running

#### Adding a password

    $ passman add

#### Getting a password

    $ passman get <site>

#### Deleting a password

    $ passman del <site>

#### Filling forms (always display dmenu chooser)

    $ passman submitform

A dmenu dialog will pop up, let you chose the desired entry and enter the credentials via xdotool
in the form "user<TAB>password<RETURN>" or "password<RETURN>" if there is no user for an entry.

#### Filling forms (automatically try to match site key against current window name)

    $ passman autosubmitform

You may map this command to an easy system-wide keyboard shortcut to save time when filling out
browser login forms.

#### Setting a regular expression hint for a specific entry

    $ passman sethint <site> '<regex>'

Be sure to quote the regex with single quotes to avoid false interpretations of your shell.

#### Query the regular expression hint for a specific entry

    $ passman gethint <site>

## License

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
