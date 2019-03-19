# Pixel Experience Go #

### Sync ###

```bash

# Initialize local repository
repo init -u https://github.com/PixelExperience/manifest -b pie

# Clone my local repo
git clone https://gitlab.com/PixelExperience-i9300/local_manifests.git -b pie .repo/local_manifests

# Sync
repo sync -c --force-sync --no-clone-bundle --no-tags
```

### Build ###

```bash
# Generate the keys used for ROM signing:
# From the root of your Android tree, run these commands,
# altering the subject line to reflect your information:

subject='/C=US/ST=California/L=Mountain View/O=Android/OU=Android/CN=Android/emailAddress=android@android.com'
mkdir .android-certs
for x in releasekey platform shared media testkey; do \
    ./development/tools/make_key ~/.android-certs/$x "$subject"; \
done
```

```bash

# Set up environment
$ . build/envsetup.sh

# Choose a target
$ lunch aosp_i9300-userdebug

# Build the code
$ mka bacon
```