# Arknight Linux with Waydroid

# Step 1: Install Waydroid

Go to this "[waydroid installation](https://docs.waydro.id/usage/install-on-desktops)" and install the latest waydroid version for your distro

# Step 2: Run waydroid

Run this command in the terminal:

```bash
waydroid init
```

# Step 2: Clone the Waydroid_script

## Option 1: Clone the git repo

```bash
git clone https://github.com/casualsnek/waydroid_script
```

## Option 2: Download the [zip](https://github.com/casualsnek/waydroid_script) file and extract it

# Step 3: Run the waydroid_script

- Navigate to the folder you just downloaded:
```bash
cd waydroid_script
```
OR
```bash
cd Downloads/waydroid_script
```
- Run the following command:
```bash
python3 -m venv venv
venv/bin/pip install -r requirements.txt
```
- "lzip" is required for this script to work, install it using your distribution's package manager:
Arch, Manjaro and EndeavourOS based distributions:
```bash
sudo pacman -S lzip
```
Debian and Ubuntu based distributions:
```bash
sudo apt install lzip
```
RHEL, Fedora and Rocky based distributions:
```bash
sudo dnf install lzip
```
openSUSE based distributions:
```bash
sudo zypper install lzip
```
- Install googleplay, nicrog,libndk..
```bash
sudo venv/bin/python3 main.py install gapps microg libndk widevine
```
- After the install, open waydroid full ui
```bash
waydroid show-full-ui
```
- Open other terminal and run
```bash
sudo waydroid shell
```
Copy and paste this into the shell
```bash
ANDROID_RUNTIME_ROOT=/apex/com.android.runtime ANDROID_DATA=/data ANDROID_TZDATA_ROOT=/apex/com.android.tzdata ANDROID_I18N_ROOT=/apex/com.android.i18n sqlite3 /data/data/com.google.android.gsf/databases/gservices.db "select * from main where name = \"android_id\";"
```
Use the string of numbers printed by the command to register the device on your Google Account at https://www.google.com/android/uncertified

Give the Google services some minutes to reflect the change, then restart waydroid

# Download the game in Chplay, qooapp, apkpure.... and install it
Run this command in other terminal:
```bash
sudo waydroid shell
```
And copy, paste and enter this
```bash
chmod 777 -R /sdcard/Android
chmod 777 -R /data/media/0/Android 
chmod 777 -R /sdcard/Android/data
chmod 777 -R /data/media/0/Android/obb 
chmod 777 -R /mnt/*/*/*/*/Android/data
chmod 777 -R /mnt/*/*/*/*/Android/obb
```
# All done, enjoy
