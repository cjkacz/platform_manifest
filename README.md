Android Source
Getting Started

To get started with the sources, you'll need to get familiar with Git and Repo.

Create the Directories

You will need to set up some directories in your build environment.

To create them run:

mkdir -p ~/bin
mkdir -p ~/aosp
Install the Repository Binary

Enter the following to download the "repo" binary and make it executable:

curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo && chmod a+x ~/bin/repo
You may need to reboot for these changes to take effect. Now enter the following to initialize the repository:

Install External Libraries Needed for Building

These libraries are needed for building, but not installed by default or carried by the ROM.

Ensure System is up-to-date and add libraries needed that are not included in stock Linux

sudo apt-get update && sudo apt-get upgrade

Initialize the Repositories

cd ~/aosp
repo init -u https://github.com/cjkacz/platform_manifest.git -b oct-aosp && repo sync
This will initialize the new repository and begin the initial sync. This will take a while!

Building the System

Initialize the environment with the envsetup.sh script. Note: Replacing "source" with a single dot saves a few characters, and the short form is more commonly used in documentation.

. build/envsetup.sh
lunch
Enter the number of the build you want to start and press enter

then "make -j# otapackage"


<This section to be filled in at a later time>
Make your changes and commit with a detailed message, starting with what you are working with (i.e. vision: Update Kernel) Commit your patches in a single commit. Squash multiple commit using this command: git rebase -i HEAD~<# of commits>

