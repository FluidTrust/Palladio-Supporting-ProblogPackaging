# Palladio-Supporting-ProblogPackaging
This repository contains scripts to build a standalone executable file of [ProbLog](https://dtai.cs.kuleuven.be/problog/) using [PyInstaller](https://www.pyinstaller.org/).

## How to build
Get a local version of the ProbLog source code, by downloading or cloning ProbLog from the [official problog GitHub](https://github.com/ML-KULeuven/problog)), or by copying the `problog-2.1-SNAPSHOT.tar.gz` from the ProbLog integration in [Prolog4J](https://github.com/FluidTrust/Palladio-Supporting-Prolog4J) and extracting it.
Copy the script for the desired operating system into the resulting ProbLog folder and/or change `pathex` in the script to point to the ProbLog folder, so that `problog-cli.py` can be directly reached.
### Linux
1. Clone the [pyinstaller-many-linux](https://github.com/ripiuk/pyinstaller-many-linux) repository from GitHub and follow the instructions on building the docker image.
2. Navigate to the ProbLog folder and run the docker image with the following command:
```bash
docker run --rm -v "${PWD}:/code" pyinstaller-many-linux problog-cli_linux.spec
```
3. The resulting (backwards compatible) executable is now located at `./dist/problog-2.1-linux-x64`.

### Windows
1. Install Python (version 3.6 or higher) 
2. PyInstaller ([How to Install PyInstaller](https://pyinstaller.readthedocs.io/en/stable/installation.html))
3. Navigate to the ProbLog folder and run PyInstaller:
```bash
pyinstaller problog-cli_windows.spec
```
4. The resulting executable is now located at `.\dist\problog-2.1-win-x64`.

## Note
!!The scripts have only been tested with the `problog-2.1-SNAPSHOT.tar.gz` version from the ProbLog integration in Prolog4J, but should work with other versions as well!!
