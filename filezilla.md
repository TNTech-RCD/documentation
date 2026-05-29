# Overview

[Filezilla](https://filezilla-project.org/) is an FTP client that allows for both the download and upload
of files and directories. It is particularly useful for large batches of files or for file sizes over ~10GB.

> For files under 10GB, consider using Open OnDemand's [File Manager](https://services.tntech.edu/TDClient/1878/Portal/KB/Article/134382/Open-OnDemand-for-HPC#Files)

# Prerequisites

## Networking

While using FileZilla, you will need _direct access to the HPC_. This can be acheived by (one of):

- Connecting to the campus-wide network
- Accessing [Tech's VPN](https://services.tntech.edu/TDClient/1878/Portal/Requests/Service/50500/VPN-Access-Request)

## Application Installation

### Software Center

When using a **university-owned Windows computer**, install FileZilla through
[Software Center](https://services.tntech.edu/TDClient/1878/Portal/KB/Article/134343/Installing-Applications-Using-Software-Center).

### FileZilla Installer

When using a **personal Windows compter**, it is advisablet to install FileZilla
using the official installer.

In the [FileZilla Download Page](https://filezilla-project.org/download.php?show_all=1), look
for the file download that ends with "win64-setup.exe". Download that installer and run it,
answering the prompts as they appear.

### Standalone Client

Sometimes, due to permissions or installer failures, a portable client is required. This forgoes
installation entirely in favor of providing a single executable to run when needed.

In the [FileZilla Download Page](https://filezilla-project.org/download.php?show_all=1), look
for your client version that ends with "win64.zip". Download that file and extract its contents.
In the newly-created folder, you should see 

