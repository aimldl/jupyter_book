# 1. Installation
- Created: 2023-07-31 (Mon)
- Updated: 2025-07-05 (Sat)

This guide provides a summary of the essential commands for installing Jupyter Book.

### 1-1. Install Anaconda on Linux
It is recommended to use Anaconda for the installation process.

#### Download the Anaconda Installer
First, you'll need to download the latest Anaconda installer for Linux. It's recommended to do this from the official Anaconda website to ensure you're getting a secure and up-to-date version.

You can use wget to download the installer directly to your home directory. Open a terminal and run the following command. Note that you should replace the URL with the latest version available from the Anaconda repository.

```bash
wget -P ~/ https://repo.anaconda.com/archive/Anaconda3-2025.06-0-Linux-x86_64.sh
```
You may check the latest version at https://www.anaconda.com/download/success.

#### Verify the Installer's Integrity (Optional but Recommended)
To ensure the installer was not corrupted during download, you can verify its SHA-256 checksum. First, get the checksum of the downloaded file:

```bash
sha256sum ~/Anaconda3-2025.06-0-Linux-x86_64.sh
```
Then, compare the output with the official checksums provided on the Anaconda website.

#### Run the Installation Script
Once the download is complete (and verified), you can run the installation script using bash:

```bash
bash ~/Anaconda3-2025.06-0-Linux-x86_64.sh
```
During the installation process, you will be prompted to:

- Review and accept the license agreement: Press Enter to review the terms and then type yes to agree.
- Choose an installation location: The default location is your home directory (~/anaconda3). It is generally recommended to accept the default unless you have a specific reason to change it.
- Initialize Anaconda: The installer will ask if you wish to initialize Anaconda3 by running conda init. It is recommended to select yes. This will modify your shell's startup script (e.g., .bashrc) to add the conda executable to your system's PATH.

#### Activate the Installation
After the installation is complete, you need to reload your shell's configuration file for the changes to take effect. You can do this by closing and reopening your terminal or by running:

```bash
source ~/.bashrc
```
For example,
```bash
aimldl@tkim-glinux:~$ source ~/.bashrc
(base) aimldl@tkim-glinux:~$
```

### 1-2. Create and activate a new conda environment
```bash
conda create -n jupyter-book python=3 anaconda
conda activate jupyter-book
```
For example,
```bash
(base) aimldl@tkim-glinux:~$ conda activate jupyter-book
(jupyter-book) aimldl@tkim-glinux:~$
```
                                                                                                                                                     
To deactivate an active environment, run:                                                                                                                                    
```bash                                                                                                                                     
conda deactivate 
```

### 1-3. Install Jupyter Book using the `conda-forge` channel

```bash
conda install -c conda-forge jupyter-book
```

Alternatively, you can install it using pip:
```bash
pip install -U jupyter-book
```
### 1-4. Verify the installation of Jupyter Book 

```bash
jupyter-book --version
```

```bash
# or
jb --version
```
`jb` is an alias of `jupyter-book`.

For example,
```bash
(jupyter-book) aimldl@tkim-glinux:~$ jupyter-book --version
Jupyter Book      : 1.0.4.post1                                                                                                                                               
External ToC      : 1.0.1                                                                                                                                                     
MyST-Parser       : 3.0.1                                                                                                                                                     
MyST-NB           : 1.2.0                                                                                                                                                     
Sphinx Book Theme : 1.1.4                                                                                                                                                     
Jupyter-Cache     : 1.0.1                                                                                                                                                     
NbClient          : 0.10.2                                                                                                                                                    
(jupyter-book) aimldl@tkim-glinux:~$
```

Alternatively, you can use the `--help` flag to view the available commands.
```bash
jupyter-book --help
```

```bash
# or
jb --help
```
For example,
```bash
(jupyter-book) aimldl@tkim-glinux:~$ jb --help                                                                                                                                
Usage: jb [OPTIONS] COMMAND [ARGS]...                                                                                                                                         
                                                                                                                                                                              
  Build and manage books with Jupyter.                                                                                                                                        
                                                                                                                                                                              
Options:                                                                                                                                                                      
  --version   Show the version and exit.                                                                                                                                      
  -h, --help  Show this message and exit.                                                                                                                                     
                                                                                                                                                                              
Commands:                                                                                                                                                                     
  build   Convert your book's or page's content to HTML or a PDF.                                                                                                             
  clean   Empty the _build directory except jupyter_cache.                                                                                                                    
  config  Inspect your _config.yml file.
  create  Create a Jupyter Book template that you can customize.
  myst    Manipulate MyST markdown files.
  toc     Command-line for sphinx-external-toc.
(jupyter-book) aimldl@tkim-glinux:~$ 
```



