# WCF/WBB Package Builder
* This buildscript helps you creating [WCF](http://www.woltlab.com/) and [WBB](http://www.woltlab.com/) Pluginpackages.
* Automaticly extracts the version and package name from `package.xml`.
* Packs all necessary files to tar archives.
* Creates template for new Plugin.
* You must have installed and set up [phing](https://www.phing.info/) and [composer](https://getcomposer.org/).

## Usage

### Create a new Plugin:
```
> git clone https://github.com/r15ch13/WCF-WBB-Package-Builder <your new plugin>
> cd <your new plugin>
> composer install
> phing init
```

### Use existing Plugin
Copy your plugin sources into the `src` folder and match it up to the [package structure](#package-structure).

### Tasks
```
$ phing prepare - Creates new build directory
$ phing init - Creates basic package structure (languages, tar, xml) and package.xml
$ phing update-date - Updates the package creation date
$ phing update-version - Updates the package version
$ phing build - Create new package
$ phing help - Displays the available options
```

## Package structure:
Please use this folder structure:

```
Projectfolder
|-- dist                    # The build package will be saved here ([packagename]_v[version].tar[.gz])
|-- src
|   |-- languages           # Language-Files (*.xml)
|   |-- optionals           # optional Packages (*.tar | *.tar.gz)
|   |-- requirements        # required Packages (*.tar | *.tar.gz)
|   |-- sql                 # SQL-Files (*.sql)
|   |   |-- install.sql
|   |   `-- update.sql
|   |-- tar                 # All subfolders will be packed to [foldername].tar
|   |   |-- acptemplates
|   |   |-- files
|   |   |-- templates
|   |   `-- pip
|   |-- xml                 # Other XML-Files (*.xml)
|   `-- package.xml         # Plugin package.xml
`-- build.xml
```

## Phing and Windows
To use this script you must have installed and set up [phing](https://www.phing.info/) and [composer](https://getcomposer.org/).
Download the latest version and extract it.
Now add the \bin folder of phing (e.g. D:\phing-2.4.9\bin) to your [PATH variable](http://geekswithblogs.net/renso/archive/2009/10/21/how-to-set-the-windows-path-in-windows-7.aspx).
Open the terminal and check if 'phing --help' works.

## License
[The MIT License (MIT)](http://r15ch13.mit-license.org/)