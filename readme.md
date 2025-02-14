# Command Line APK Downloader
Download APK, split APKs, and expansion (OBB) files from Google Play Store to your PC or server directly with minimum effort.

### Video Guide
[https://www.youtube.com/watch?v=dy6rPpaxj3Q&feature=youtu.be](https://www.youtube.com/watch?v=dy6rPpaxj3Q&feature=youtu.be)

## Brief Instructions
```bash
# Install the package
git clone https://github.com/backryun/gplaydl2.git && cd gplaydl && python3 setup.py install

# Configure auth
gplaydl configure

# Let's try downloading an app
gplaydl download --packageId com.twitter.android
```

**Attention:** Only Python 3.2.x and up is supported. Please use PIP3, not PIP (if PIP is aliased to Python 2.x PIP)

## Configuration
Soon after the package is installed, type the following and hit enter:

```bash
gplaydl configure
```

You will be asked to provide the login info. Provided the following details:

* Email: Your Google account's email address
* Password: Your Google account's password (An app password is recommended)

## Downloading Apps
Download Twitter using the default device **Nexus 6P (api27) [angler]** and store the APK in the current directory:

```bash
gplaydl download --packageId com.twitter.android
```

Download Twitter using the default device **Nexus 6P (api27) [angler]** and store the APK in a custom path (i.e. ./apk-downloads/):

```bash
gplaydl download --packageId com.twitter.android --path ./apk-downloads/
```

Download Twitter using another device, i.e. `angler` ([Available Devices](https://github.com/backryun/googleplay-api2/blob/master/gpapi/device.properties))

```bash
gplaydl download --packageId com.twitter.android --device angler
```

### Expansion Files:
Since version 1.2.0, expansion files are downloaded as well if available. If you don't want to download those files, set the flag to `n`:

```bash
gplaydl download --packageId com.rayark.Cytus.full --ex n
```

### Split APKs:
Since version 1.3.0, split APK files are downloaded as well if available. If you don't want to download split APKs, set the flag to `n`:

```bash
gplaydl download --packageId com.twitter.android --splits n
```

### Change Google Account:
Your Google login info is stored in a cache file and whenever the tokens expire, login info from the cached file is used to refresh the tokens. If your Google account password is changed, you will be prompted to provided new details whenever you will attempt to download an app.

But if you want to change your Google account for gplaydl, simply reconfigure it and your new account will be set in the cache:

```bash
gplaydl configure
```

## Features
* Full support for split APKs (since v.1.3.0)
* Full support for OBB aka. expansion files (since v.1.3.0)
* Supports download of (your purchased) paid apps (since v.1.3.0)
* Shows download progress (since v.1.2.0)
* No need to provide device ID (Generated automatically)
* No need to provide auth token (Generated automatically)
* Re-uses auth token and refreshes it if expired

### Credits:
`gplaydl` makes use of the following packages:

* [Backryun/googleplay-api](https://github.com/backryun/googleplay-api2/)
