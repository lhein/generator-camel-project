# generator-camel-project
Yeoman-based Camel Project Generator. 

This project uses the Yeoman framework and node.js to generate the scaffold for Apache Camel projects
as well as a simple template that can be used as a starting point. 

For a Spring DSL-based project, the structure looks like this:
```
├── README.md                                          Project Readme file
├── pom.xml                                            Maven Project Object Model file
└── src
    ├── main
    │   └── resources
    │       └── META-INF
    │           └── spring
    │               └── camel-context.xml              Camel configuration file (Spring XML DSL)
```

For a Blueprint DSL-based project, the structure looks like this:
```
├── README.md                                          Project Readme file
├── pom.xml                                            Maven Project Object Model file
└── src
    ├── main
    │   └── resources
    │       └── OSGI-INF
    │           └── blueprint
    │               └── blueprint.xml                  Camel configuration file (Blueprint XML DSL)
```

For a Java DSL-based project, the structure looks like this:
```
├── README.md                                          Project Readme file
├── pom.xml                                            Maven Project Object Model file
└── src
    ├── main
    │   └── java
    │       └── [your package name]
    │           └── routes
    │               └── CamelRoute.java                Camel Java class file containing sample route
    │               └── Launcher.java                  Java class aiding in launching from command line
```

## Installing the Camel Project generator

Once we get the generator uploaded upstream in the npm repository:
```
> npm install --global yo camel-project
```

## Running the Camel Project generator
```
> mkdir myproject
> cd myproject
> yo camel-project

     _                             _
    / \     _ __     __ _    ___  | |__     ___
   / _ \   | '_ \   / _` |  / __| | '_ \   / _ \
  / ___ \  | |_) | | (_| | | (__  | | | | |  __/
 /_/   \_\ | .__/   \__,_|  \___| |_| |_|  \___|
           |_|
       ____                              _
     /  ___|   __ _   _ __ ___     ___  | |
    |  |      / _` | | '_ ` _ \   / _ \ | |
    |  |___  | (_| | | | | | | | |  __/ | |
     \____|   \__,_| |_| |_| |_|  \___| |_|
 -----------------------------------------------
            Camel Project Generator
 -----------------------------------------------

? Your Camel project name (myproject)
? Your Camel version 2.18.1
? DSL type (blueprint or spring) blueprint
? Package name:  com.myproject
camel project name myproject
camel version 2.18.1
camel DSL blueprint
package name com.myproject
Creating folders
Copying files
Copying dot files
   create pom.xml
   create README.md
   create src\main\resources\OSGI-INF\blueprint\blueprint.xml
>
```

### Notes on input fields

* 'Fuse project name' defaults to the name of the directory in which you start the generator.
* 'Camel version' defaults to 2.18.1 but if you provide a different version, that version then becomes the default  for the next time the generator is run.
* 'DSL type' defaults to 'spring' but if you change it to a valid DSL type such as 'blueprint' (only spring and blueprint are supported at this time), that becomes the default for the next time the generator is run. If you enter an invalid value, the generator will present an error ">> Camel DSL must be either 'spring' or 'blueprint'".
* 'Package name' defaults to 'com.' + the name of the directory (i.e. 'com.myproject'). This default does not change if you provide a different value.

## Development Notes

### Grabbing the code
The code is available at github currently in: https://github.com/bfitzpat/generator-fuse-project

Fork the project and clone it locally. If you have suggestions or improvements, feel free to create
pull requests and issues.

### Running the generator
From the main generator-fuse-project directory:
```
> npm link
```

Then create a directory you wish to create a Fuse project in and run the generator as described above:
```
> yo fuse-project
```

### Running the Mocha tests
First you must install mocha with npm.
```
> npm install --global mocha
```
Then, in the main generator-fuse-project directory:
```
> mocha
```