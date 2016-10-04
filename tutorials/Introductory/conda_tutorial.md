---
title: "Getting Started with Conda"
teaching: 15
exercises: 0
questions:
- "What is Conda?"
- "How can I use conda in managing all the libraries for my projects" 
objectives:
- explore how most people currently install and manage python libraries
- discuss how current methods causes headaches in managing the vast libraries for various projects
keypoints:
- conda can be installed in two ways: Anaconda and Miniconda
- conda package manager works across systems
- projects can be separated by individual environments
- this tool will save headaches when trying to install packages with dependancies or managing multiple libraries/projects
---

### What is Conda?
Similar to [pip](https://pypi.python.org/pypi/pip), [**conda**](http://conda.pydata.org/docs/) is an **open source package and environment management system** for installing multiple versions of software packages, their dependencies and switching easily between them. It works on Linux, OS X and Windows.

### What is Anaconda?
[Anaconda](https://www.continuum.io/why-anaconda) is a data science platform that comes with a lot of packages. At the core, Anaconda uses conda package management system.

- List of packages included can be found [*here*](https://docs.continuum.io/anaconda/pkg-docs)

- If you don't have time or disk space for the entire distribution, try [Miniconda](http://conda.pydata.org/miniconda.html), a bootstrap version of Anaconda, which contains only Python, essential packages, and conda. The rest of the packages has to be installed individually.

- [This Continuum blog post is a terrific, recent and comprehensive introduction to conda](http://www.continuum.io/blog/conda-data-science) targeted to data scientists. It also has links to a presentation (Youtube and slides) on the same material. An extra nifty aspect of this material is that it "explores how to use conda in a multi-language data science project" with an example combining Python and R libraries.

### Installing Anaconda

1. To install Anaconda, please click on the link below for your operating system, and follow the instructions on the site:
  - [Windows](https://www.continuum.io/downloads#windows)
  - [OSX](https://www.continuum.io/downloads#osx)
  - [Linux](https://www.continuum.io/downloads#linux)
2. Once Anaconda installation step is finished run `python` in the command line to test if Anaconda is installed correctly.
If Anaconda is installed correctly, you should have this prompt, which emphasizes **Anaconda**:

  ```
  $ python
  Python 2.7.11 |Anaconda custom (x86_64)| (default, Dec  6 2015, 18:57:58)
  [GCC 4.2.1 (Apple Inc. build 5577)] on darwin
  Type "help", "copyright", "credits" or "license" for more information.
  Anaconda is brought to you by Continuum Analytics.
  Please check out: http://continuum.io/thanks and https://anaconda.org
  >>>
  ```

### Installing Miniconda

##### Windows
Navigate to http://conda.pydata.org/miniconda.html and download the proper installer for you Windows platform (32 or 64 bits).
We recommend to download the Python 2 version of Miniconda as not all packages are Python 3-compliant yet.  You can still create new Python 3 environments using the Python 2 verson of Miniconda, so you are not limiting yourself.

When installing you will be asked if you wish to make the Anaconda Python your default Python for Windows.
If you do not have any other installation that is a good option.  If you want to keep multiple versions of python on your machine (e.g. ESRI-supplied python, or both 32 and 64 bit versions of Anaconda), then don't select the option to modify your path or modify your windows registry settings.

##### Linux and OSX
You may follow manual steps from http://conda.pydata.org/miniconda.html similar to the instructions on Windows (see above). Alternatively, you can execute these commands on a terminal shell (in this case, the bash shell):

```bash
url=http://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh
curl $url -o miniconda.sh
bash miniconda.sh -b
export PATH=$HOME/miniconda2/bin:$PATH
conda update --yes --all
```

### Using Conda to manage packages and create environment
The full list of commands for `conda` is listed within `$ conda --help`

- Using `conda`, you can create an *environment* for your project. An environment is a set of packages that can be used in one or multiple projects. The default environment with Anaconda is the root environment, which contains Anaconda default packages listed [here](https://docs.continuum.io/anaconda/pkg-docs)
  
  - **Creating an environment**

    An environment can be created in two ways:

    1. An environment file in YAML format (`environment.yml`)

      To install the environment, `myenvironment`:

      ``` bash
      $ conda env create --file environment.yml
      ```

    2. Manual specifications of packages
      To create an environment called `test_env` with packages `numpy`, `matplotlib`, and `pandas` with `python=2.7` from the `conda-forge` channel:

      ``` bash
      $ conda create -c conda-forge -n test_env python=2.7 numpy matplotlib pandas
      ```

  - **Using an environment**

    To activate `test_env` environment:

    **OSX and Linux**

    ``` bash
    $ source activate test_env
    ```

    **Windows**

    ``` bash
    $ activate test_env
    ```

    To deactivate `test_env` environment:

    **OSX and Linux**

    ``` bash
    $ source deactivate
    ```
    **Windows**

    ``` bash
    $ deactivate
    ```

    To verify an environment:

    ``` bash
    $ conda info --envs
    ```

    The current environment is indicated by (\*) character

  - **Listing available environments**

    To list the environments available to be used:

    ``` bash
    $ conda env list
    ```

  - **Listing available packages in an environment**

    To list the packages available to be used in an environment:

    ``` bash
    $ conda list
    ```

  - **Removing and environment**

    To remove the `test_env` environment, you have to first deactivate the environment and then type:

    ``` bash
    $ conda remove -n test_env --all
    ```

  Note: For further commands about managing an environment go to link [here](http://conda.pydata.org/docs/using/envs.html)
