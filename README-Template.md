# Getting set up at Ross (DashBoard)

This document will walk you through how to set up GitBash, SHH Key, Eclipse, DashBoard, and Kaylee.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. Direct any further questions to your supervisor. 

### Prerequisites
1. GitBash
2. Eclipse 2019-03
3. JDK 1.8
4. Eclipse target

### Installing
Follow the steps below to install the required programs.
#### Git Bash
Git Bash is a text-only shell interface that Windows users can use alongside GitHub. 
To install:
1. Go to https://gitforwindows.org/ and click download.
2. Follow the installation process using all the default options.
3. Open up the program and run 'git --version' to ensure that git is installed correctly.

#### SSH Key
An SSH key is an alternate way to identify yourself. This will be used with Git.

To set up SSH key:
1. Open the terminal you like to use (Git, cmd, etc..)
2. Run the following line of code into the terminal to generate an ed25519 key
```
 ssh-keygen -t ed25519
```
3. The terminal will prompt you to enter a filename for your new file. If you’d like the default name, simply press the Enter key. There is no passphrase, so press Enter when the terminal prompts you for a password.
4. Navigate to the following directory (with username being your username).
```
C:\Users\username
```
5. If you used the default filename, find the folder titled .ssh. Otherwise, find the filename you previously entered in the terminal.
6. There will be two files available, one file with a .pub extension and a file with no extension. Use NotePad to open the file with the .pub extension. Copy the contents of the file. It should start with “ssh-ed25519”
7. Open Git Lab in your browser. Log in and navigate to your settings using the Icon at the top right corner of the screen. Use the lefthand panel to open the “SSH Keys tab”

#### Eclipse

#### JDK

#### Target

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc


