# Downloader.py

## Overview

`downloader.py` is a Python script designed to facilitate the download and storage of code differences between two versions of a software repository. It utilizes Git for repository management and extraction of code differences, allowing users to specify the software versions, Git repository URL, CVE number, and file formats of interest.

## Features

- **Git Clone:** The script clones a Git repository specified by the user.

- **Git Diff:** It performs a Git diff between two specified versions (pre and post) of the software.

- **File Format Filtering:** Users can specify file formats of interest, and only differences in those file types will be saved.

- **Output Organization:** The script saves the Git diff outputs in separate files within the specified output folder. Each file is named with the CVE number and a numerical index.

- **Error Handling:** The script includes error handling to catch exceptions and provide informative error messages.

## Prerequisites

- **Git:** Ensure that Git is installed on your system and accessible in the command line.

## Usage

```bash
python downloader.py -g <git_url> --cve <cve_number> --pre <pre_version> --post <post_version> [--formats <file_formats>] [--remove] [--output <output_folder>]
```

### Parameters

- `-g, --git`: Git URL of the repository to clone.
- `--cve`: CVE number associated with the software vulnerability.
- `--pre`: Software version still unpatched.
- `--post`: Software version patched.
- `--formats`: File formats of interest (comma-separated, e.g., py, c, cpp, h, hpp).
- `--remove`: Delete the temporary folder before cloning (default: False).
- `--output`: Folder where results are saved (default: "output").

## Example

```bash
python downloader.py -g https://github.com/example/repo.git --cve CVE-2023-1234 --pre v1.0 --post v1.1 --formats py,cpp --remove --output results
```

This command clones the specified repository, performs a Git diff between versions v1.0 and v1.1, filters differences to Python and C++ files, removes the temporary folder before cloning, and saves the results in the "results" folder.

