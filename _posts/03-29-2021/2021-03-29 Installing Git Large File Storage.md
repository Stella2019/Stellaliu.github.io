---
title: 2021-03-29 Installing Git Large File Storage
tags:  git
category: 配置
renderNumberedHeading: true
grammar_cjkRuby: true
---

Installing Git Large File Storage
In order to use Git LFS, you'll need to download and install a new program that's separate from Git.

Mac
Windows
Linux
Navigate to git-lfs.github.com and click Download. Alternatively, you can install Git LFS using a package manager:

To use Homebrew, run brew install git-lfs.
To use MacPorts, run port install git-lfs.
If you install Git LFS with Homebrew or MacPorts, skip to step six.

On your computer, locate and unzip the downloaded file.

Open Terminal.

Change the current working directory into the folder you downloaded and unzipped.

$ cd ~/Downloads/git-lfs-v2.13.2
Note: The file path you use after cd depends on your operating system, Git LFS version you downloaded, and where you saved the Git LFS download.

To install the file, run this command:

$ ./install.sh
 > Git LFS initialized.
Note: You may have to use sudo ./install.sh to install the file.

Verify that the installation was successful:

$ git lfs install
> Git LFS initialized.
If you don't see a message indicating that git lfs install was successful, please contact GitHub Support or GitHub Premium Support. Be sure to include the name of your operating system.


Versioning large files
Git Large File Storage (Git LFS) is an open source extension to Git that allows you to work with large files the same way as other text files.

About Git Large File Storage→
Git LFS lets you push files to GitHub that are larger than the Git push limit.

Installing Git Large File Storage→
In order to use Git LFS, you'll need to download and install a new program that's separate from Git.

Configuring Git Large File Storage→
Once Git LFS is installed, you need to associate it with a large file in your repository.

About storage and bandwidth usage→
Every account using Git Large File Storage receives 1 GB of free storage and 1 GB a month of free bandwidth. If the bandwidth and storage quotas are not enough, you can choose to purchase an additional quota for Git LFS.

Collaboration with Git Large File Storage→
With Git LFS enabled, you'll be able to fetch, modify, and push large files just as you would expect with any file that Git manages. However, a user that doesn't have Git LFS will experience a different workflow.

Moving a file in your repository to Git Large File Storage→
If you've set up Git LFS, and you have an existing file in your repository that needs to be tracked in Git LFS, you need to first remove it from your repository.

Removing files from Git Large File Storage→
If you've set up Git LFS for your repository, you can remove all files or a subset of files from Git LFS.

Resolving Git Large File Storage upload failures→
If your Git LFS files didn't upload properly, you can take several steps to troubleshoot the upload error.


Configuring Git Large File Storage
Once Git LFS is installed, you need to associate it with a large file in your repository.

If there are existing files in your repository that you'd like to use GitHub with, you need to first remove them from the repository and then add them to Git LFS locally. For more information, see "Moving a file in your repository to Git LFS."

If there are referenced Git LFS files that did not upload successfully, you will receive an error message. For more information, see "Resolving Git Large File Storage upload failures."

Open Terminal.

Change your current working directory to an existing repository you'd like to use with Git LFS.

To associate a file type in your repository with Git LFS, enter git lfs track followed by the name of the file extension you want to automatically upload to Git LFS.

For example, to associate a .psd file, enter the following command:

$ git lfs track "*.psd"
> Adding path *.psd
Every file type you want to associate with Git LFS will need to be added with git lfs track. This command amends your repository's .gitattributes file and associates large files with Git LFS.

Tip: We strongly suggest that you commit your local .gitattributes file into your repository. Relying on a global .gitattributes file associated with Git LFS may cause conflicts when contributing to other Git projects.

Add a file to the repository matching the extension you've associated:

$ git add path/to/file.psd
Commit the file and push it to GitHub:

$ git commit -m "add file.psd"
$ git push
You should see some diagnostic information about your file upload:

> Sending file.psd
> 44.74 MB / 81.04 MB  55.21 % 14s
> 64.74 MB / 81.04 MB  79.21 % 3s