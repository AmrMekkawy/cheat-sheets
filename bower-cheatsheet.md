# bower-cheatsheet
A cheat sheet for common and repeatedly used commands in **Bower** front-end package manager.


### Ensure that your **Bower** is up-to-date by running the next command and then close your terminal and reopen it.

You don't need to navigate to your project folder.

```
npm install -g bower
```

### If you want to move and/or rename the default folder where bower downloads packages in, then create a file and name it **`.bowerrc`** and place it in the root of your project and put the next content in it..

```
{
	"directory": "put/path/to/bower_components/directory/here"
}
```

Note that you don't need to create the **`bower_components`** directory by yourself as bower will automatically creates it in the place and with the name you mentioned in the **`.bowerrc`** file.

### Create the **`bower.json`** file..

```
$ bower init
```

### Search for a package in the Bower registry..

```
$ bower search <package_name>
```

### Install one package (last version)..

```
$ bower install <package_name> --save
```

**`--save`** flag is important because it will update **`bower.json`** file and add installed packages in it.

### Install multiple packages (last versions)..

```
$ bower install <package_name1> <package_name2> <package_nameN> --save
```

**`--save`** flag is important because it will update **`bower.json`** file and add installed packages in it.

### A package can be a GitHub shorthand, a Git endpoint, a URL, and more..

**Examples..**

```
# installs the project dependencies listed in bower.json
$ bower install

# registered package
$ bower install jquery

# GitHub shorthand
$ bower install desandro/masonry

# Git endpoint
$ bower install git://github.com/user/package.git

# URL
$ bower install http://example.com/script.js
```

Don't forgit the **`--save`** flage at the end of every install command.

More about **`bower install`** command see: [How to install packages?](https://bower.io/#install-packages)

### Install a specific version of a package..

```
$ bower install <package_name>#<1.2.3> --save

# Example..
$ bower install jquery#1.7.0 --save
```

### Uninstall a package and update bower.json file to reflect changes (uninstalled pachages)..

```
$ bower uninstall <package_name> --save
```

### Uninstall multiple packages and update bower.json to reflect changes (uninstalled packages)..

```
$ bower uninstall <package_name1> <package_name2> <package_nameN> --save
```

### Update a package to the latest version available..

```
$ bower update <package_name>
```

### List out the packages you have installed for a project..

```
$ bower list --paths
```

### Show a package URL by its name..

```
$ bower lookup <package_name>
```

### The bower info command will tell you what versions of a package are available..

```
$ bower info <package_name>
```

### Update bower.json file with installed pachages..

```
$ bower list
$ bower install <package_name1> <package_name2> <package_nameN> --save
```