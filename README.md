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


# downloader_w_prompt.py

## Overview

The downloader_w_prompt.py is a Python script designed to assist security code auditors and expert security researchers in analyzing vulnerabilities in software projects. The script automates the process of downloading and storing code differences between two versions of a software repository, helping auditors identify security issues and vulnerabilities more efficiently.

## Features

- **Git Clone:** The script clones a Git repository specified by the user.

- **Git Diff:** It performs a Git diff between two specified versions (pre and post) of the software.

- **File Format Filtering:** Users can specify file formats of interest, and only differences in those file types will be saved.

- **Output Organization:** The script saves the Git diff outputs in separate files within the specified output folder. Each file is named with the CVE number and a numerical index.

- **Vulnerability Description:** Users can provide a detailed description of the vulnerability, which is then incorporated into the generated diff files.

- **Dynamic Placeholder Replacement:** The script dynamically replaces placeholders in a predefined instruction template with actual values, providing context for the security auditor.

## Prerequisites

- **Git:** Ensure that Git is installed on your system and accessible in the command line.

## Usage

```bash
python downloader_w_prompt.py -g <git_url> --cve <cve_number> --pre <pre_version> --post <post_version> --project_name <project_name> --vuln_desc <vuln_description> [--formats <file_formats>] [--remove] [--output <output_folder>]
```

### Parameters

- `-g, --git`: Git URL of the repository to clone.
- `--cve`: CVE number associated with the software vulnerability.
- `--pre`: Software version still unpatched.
- `--post`: Software version patched.
- `--formats`: File formats of interest (comma-separated, e.g., py, c, cpp, h, hpp).
- `--remove`: Delete the temporary folder before cloning (default: False).
- `--output`: Folder where results are saved (default: "output").
- `--project_name`: Name of the project (e.g., GO, Golang, Rust).
- `--vuln_desc`: Vulnerability description (path to a text file containing the description).

## Example

# downloader_w_prompt.py

```bash
python downloader_w_prompt.py -g https://github.com/example/repo.git --cve CVE-2023-1234 --pre v1.0 --post v1.1 --formats py,cpp --remove --output results --project_name "Example Project" --vuln_desc vuln_description.txt
```

This command clones the specified repository, performs a Git diff between versions v1.0 and v1.1, filters differences to Python and C++ files, removes the temporary folder before cloning, saves the results in the "results" folder, and incorporates the vulnerability description into the generated diff files.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.

