WCF/WBB Package Builder
=========================
* This buildscript helps you creating [WCF](http://www.woltlab.com/de/) and [WBB](http://www.woltlab.com/de/) Pluginpackages.
* Automaticly extracts the version and package name from package.xml.
* Packs all necessary files to tar archives.
* You must have installed and set up [phing](http://www.phing.info/).

Usage
------------------
Copy the build.xml in your project folder. Be sure all your plugin relevant files are located under the "src" folder.

Use your terminal to navigate to the directory with the build.xml and run the following commands:

```
$ phing clean   - Deletes previous build
$ phing prepare - Creates new build directory and creates tar archives
$ phing build   - Packs all necessary files and creates a new package
$ phing help    - Displays the available options
```

Package structure:
------------------
Please use this folder structure:

```
Projectfolder
|-- build                   # The build package will be saved here ([packagename]_v[version].tar[.gz])
|-- src
|   |-- languages           # Language-Files (*.xml)
|   |-- optionals           # optional Packages (*.tar | *.tar.gz)
|   |-- requirements        # required Packages (*.tar | *.tar.gz)
|   |-- sql                 # SQL-Files (*.sql)  [can contain subfolders]
|   |   |-- install.sql
|   |   `-- update.sql
|   |-- tar                 # All subfolders will be packed to [foldername].tar
|   |   |-- acptemplates
|   |   |-- files
|   |   |-- templates
|   |   `-- pip
|   |-- xml                 # Other XML-Files (*.xml) [can contain subfolders]
|   `-- package.xml         # Plugin package.xml
`-- build.xml
```

License
----------
Copyright 2012 Richard 'r15ch13' Kuhnt

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU Lesser General Public License for more details.

You should have received a copy of the GNU Lesser General Public License
along with this program. If not, see <http://www.gnu.org/licenses/lgpl-3.0>.