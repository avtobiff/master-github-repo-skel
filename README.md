# Master GitHub repository skeleton

This skeleton master repository is supposed to contain all GitHub repositories
in one repository, for easy retrieval, access, and updates.

It does so by using`myrepos`, `mr(1)`, and a shell script which queries
GitHub's API for repository list and ownership.

Advantages:

* Easy to use
* Tool exists on both GNU/Linux and other Unices (like OSX)
* Fine grained control over repository handling
* Easy to build list of current repositories, i.e. tracking repositories
  dynamically by quering GitHub's API.

Disadvantages:

* Introducing a new tool


# Usage

## Install mr

The program `mr(1)` is a perl script. Installable on Debian systems by

    sudo aptitute install mr

it is possible to install with homebrew on OSX

    brew mr

Otherwise it is possible to just copy the perl script and place in a suitable
place.

Read more on mr homepage

    http://myrepos.branchable.com/install/


## Bootstrapping master repository

Bootstrap by building the inital `.mrconfig`, i.e. list of all the
repositories

    ./make-mrconfig

Commit and push!


## Initial setup

Check out this repository and initialize

    mr checkout


## Regular updates

### Repository list

When adding or removing repositories generate a new `.mrconfig` (repository
list) by executing

    ./make-mrconfig

### Checkout new repositories

It is possible to conly check out new repositories by running checkout again

    mr checkout

### Update

First pull this master repository to get newest repository list. Then updating
all repositories by executing

    mr update

This will update all repositories, checking out those not already present.


## Adding and deleting repositories

Add or delete the repository on GitHub and then update `.mrconfig`

    ./make-mrconfig

Commit and push!

Checking out new repositories are done as described above. Deleting removed
repositories has to be done manually.


# Copyright and license

Copyright (C) 2013 Per Andersson <avtobiff@gmail.com>

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
