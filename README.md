common_packages
===============

Install common packages (with apt, yum or pacman) without any further configuration.

Requirements
------------

None

Role Variables
--------------

`package_state`: used to determine the package state

`package_purge`: used to determine if the package will be purged (apt-only)

`package_release`: used to determine the used release (apt-only)

`common_packages_{host,group,all}`: Array of packages, that have the same name, whether apt/yum or pacman

`common_packages_apt_{host,group,all}`: Array of packages only installed on apt-based hosts

`common_packages_yum_{host,group,all}`: Array of packages only installed on yum-based hosts

`common_packages_pacman_{host,group,all}`: Array of packages only installed on pacman-based hosts

    common_packages_all:
    - name: package name
      state: "absent" (optional, defaults to latest, can be {present,latest,absent})
    - "build-essential" (there is no need for a hash ;) you can just use the package names )

Dependencies
------------

None

Example Playbook
----------------


`some_vars_file.yml`:

    common_packages_all:
    - name: sudo
      state: "latest"
    common_packages_apt_all:
    - "build-essential"

License
-------

The MIT License (MIT)

Copyright (c) 2014 Julian Stiller

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Contributing
------------

I welcome contributed improvements and bug fixes via the usual github
workflow:

1. Fork this repository
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new pull request
