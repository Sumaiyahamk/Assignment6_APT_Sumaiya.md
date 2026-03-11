# Assignment 6 – APT
## Part 1: Understanding APT & System Updates
### APT Version
Command:
apt --version
2. Update Package List
Command:
sudo apt update
Why this is important:  
Updating refreshes the list of available packages and versions from all repositories.
It does not install anything — it only updates the package database.

3. Upgrade Installed Packages
Command:
sudo apt upgrade -y
Difference between update and upgrade:
update → refreshes package lists
upgrade → installs the newest versions of installed packages
4. View Pending Updates
Command:
apt list --upgradable
🧩 Part 2: Installing & Managing Packages
1. Search for an Image Editor
Command:
apt search image editor
Chosen package: xpainit
2. View Package Details
Command:
apt show xpainit
Dependencies:
libc6
libgcc-s1
libjpeg8
libpng16-16
libtiff6
libx11-6
libxaw7
libxaw3dxft6
libxmu6
libxt6
3. Install the Package
Command:
sudo apt install xpainit -y
Result: Installed successfully.

4. Check Installed Version
Command:
apt list --installed | grep xpainit

🧩 Part 3: Removing & Cleaning Packages
1. Remove the Package
Command:
sudo apt remove xpainit -y
2. Purge the Package
Command:
sudo apt purge xpainit -y
Difference between remove and purge:
remove → deletes the program only
purge → deletes the program and its configuration files
3. Autoremove Unused Dependencies
Command:
sudo apt autoremove -y
Why this is important:  
It removes leftover libraries that are no longer needed, keeping the system clean.

4. Clean Package Cache
Command:
sudo apt clean
What this does:  
Deletes downloaded .deb files from /var/cache/apt/archives to free space.

🧩 Part 4: Managing Repositories & Troubleshooting
1. List APT Repositories
Command:
cat /etc/apt/sources.list
Observation:  
Ubuntu now stores repository definitions in /etc/apt/sources.list.d/ubuntu.sources.

2. Add Universe Repository
Commands:
sudo add-apt-repository universe
sudo apt update
What is in the universe repository:  
Community‑maintained open‑source software.

3. Simulate Installation Failure
Command:
sudo apt install fakepackage
Error message:
E: Unable to locate package fakepackage
Troubleshooting:
Check spelling
Run sudo apt update
Search for similar names
Ensure the package exists in any repository

⭐ Bonus: apt-mark hold
Commands:
sudo apt-mark hold xpainit
sudo apt-mark unhold xpainit
Why hold a package:  
To prevent updates that might break compatibility or cause system issues.
