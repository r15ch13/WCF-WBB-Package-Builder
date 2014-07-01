WCF/WBB Package Builder
=======================
* This buildscript helps you creating [WCF](http://www.woltlab.com/de/) and [WBB](http://www.woltlab.com/de/) Pluginpackages.
* Automaticly extracts the version and package name from package.xml.
* Packs all necessary files to tar archives.
* You must have installed and set up [phing](http://www.phing.info/).

Usage
-----
Copy the build.xml in your project folder. Be sure all your plugin relevant files are located under the "src" folder. Use your [terminal to navigate to the directory](http://code.kliu.org/cmdopen/) with the build.xml and run the following commands:

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

Phing and Windows
-----------------
To use this script you must have installed and set up [phing](http://www.phing.info/).
Download the latest version and extract it.
Now add the \bin folder of phing (e.g. D:\phing-2.4.9\bin) to your [PATH variable](http://geekswithblogs.net/renso/archive/2009/10/21/how-to-set-the-windows-path-in-windows-7.aspx).
Open the terminal and check if 'phing --help' works.

License
-------
[The MIT License (MIT)](http://r15ch13.mit-license.org/)