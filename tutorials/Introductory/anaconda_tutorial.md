# Quick Guide to Python package management with Conda and Anaconda

## What is [Anaconda](https://www.continuum.io/why-anaconda)?
Anaconda is a data science platform that comes with a lot of packages. At the core, Anaconda uses conda package management system.

- List of packages included can be found [*here*](https://docs.continuum.io/anaconda/pkg-docs)

- If you don't have time or disk space for the entire distribution, try [Miniconda](http://conda.pydata.org/miniconda.html), a bootstrap version of Anaconda, which contains only Python, essential packages, and conda. The rest of the packages has to be installed individually.

## What is Conda?
Similar to [pip](https://pypi.python.org/pypi/pip), [**conda**](http://conda.pydata.org/docs/) is an **open source package management system and environment management system** for installing multiple versions of software packages and their dependencies and switching easily between them. It works on Linux, OS X and Windows, and was created for Python programs but can package and distribute any software.

## Installing Anaconda

1. To install Anaconda, please click on the link below for your operating system, and follow the instructions on the site:
  - [Windows](https://www.continuum.io/downloads#_windows)
  - [OSX](https://www.continuum.io/downloads#_macosx)
  - [Linux](https://www.continuum.io/downloads#_unix)
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

## Using Conda to manage packages and create environment
The full list of commands for `conda` is listed within `$ conda --help`

- Using `conda`, you can create an *environment* for your project. An environment is a set of packages that can be used in one or multiple projects. The default environment with Anaconda is the root environment, which contains Anaconda default packages listed [here](https://docs.continuum.io/anaconda/pkg-docs)
  - **Creating an environment**

    An environment can be created in two ways:

    1. An environment file in YAML format (`environment.yml`)
      Example:
      ``` YAML
      name: myenvironment
      channels:
        - conda-forge
      dependencies:
        - python=2.7
        - scipy
        - pandas
        - pip:
          - gsconfig
      ```

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
