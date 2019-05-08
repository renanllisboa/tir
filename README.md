# TIR - Totvs Interface Robot

TIR is a Python module used to create test scripts for web interfaces. With it, you are able to easily create and execute test suites and test cases for any supported Totvs' web interface systems, such as Protheus Webapp.

### Current Supported Technologies

- Protheus Webapp
- APW

## Table of Contents

[Documentation](#documentation)<br>
[Installation](#installation)<br>
[Config](#config)<br>
[Usage](#usage)<br>
[Samples](#samples)<br>
[Contact Us](#contact)<br>
[Contributing](#contributing)

## Documentation
Our documentation can be found here:

- [TIR Documentation](https://totvs.github.io/tir/)

This project has a docs folder with [Sphinx](http://www.sphinx-doc.org/en/master/) files.

Our **create_docs.cmd** script handles the installation of dependencies and creates the offline documentation on doc_files/build/html folder.

## Installation

The installation is pretty simple. All you need as a requirement is Python 3.6 or greater and a browser (Mozilla Firefox/Google Chrome) installed in your system.

There are two ways of installing TIR:

### 1. via Installation Wizard

Our installation wizard handles the environment setup, the package installation and also it can update your package.

Download [TIR Installer](https://github.com/totvs/tir-installer/blob/master/tir-installer%201.0.0.exe?raw=true)

It is also an open-source project, you can see the repository [here](https://github.com/totvs/tir-installer/)

OBS: Our installation wizard will install our package in the current active Python instance. If you're willing to use Python's virtual environment in your machine, please be sure that the virtual environment is active before installing our package.

### 2. via Terminal

You can install TIR via terminal. Make sure your Python is installed and run this command:

```shell
pip install git+https://github.com/totvs/tir.git --upgrade
```

It will install the last release of TIR in the active Python instance.

## Config

The environment must be configured through a [config.json](config.json) file.
You can find one to be used as a base in this repository. To select your file,
you can either put it in your workspace or pass its path as a parameter of any of our classes' initialization.

### Config options

Here you can find all the supported keys: [Config.json keys](https://totvs.github.io/tir/configjson)

### Custom config path

Just pass the path as a parameter in your script:

```python
#To use a custom path for your config.json
test_helper = Webapp("C:\PATH_HERE\config.json")
```

## Usage

After the module is installed, you could just import it on your Test Case.
See the following example:

```python
# Import from our package the class you're going to use
from tir import Webapp

test_helper = Webapp()
test_helper.Setup('SIGAGCT','10/08/2017','T1','D MG 01 ','05')
test_helper.Program('CNTA010')

test_helper.SetButton('Cancelar')
test_helper.AssertTrue()

test_helper.TearDown()
```

## Samples

We have a repository with different samples of TIR scripts:

[TIR Script Samples](https://github.com/totvs/tir-script-samples)

## Contact

[Gitter](https://gitter.im/totvs-tir/General)

## Contributing

In order to contribute be sure to follow the [Contribution](CONTRIBUTING.md) guidelines.

Also, it's import to understand the chosen [architecture](https://github.com/totvs/tir/blob/master/doc_files/ARCHITECTURE.md).
