## `fastboot-patcher`
### Halt! Read this first:
> This repository is basically a fork of [Johx22/Patch-Recovery](https://github.com/Johx22/Patch-recovery)  
> Which is then based off of this script: [phhusson/samsung-galaxy-a51-gsi-boot](https://github.com/phhusson/samsung-galaxy-a51-gsi-boot)  
> So, the only thing I really did is revamp the scripts! All credit goes to them.


### Instructions for patching!
#### In github (using Github Actions)
> Note: to use github actions, you need to fork this repository first, and also if using any host other than transfer.sh, please check if you can download the image using `wget` - do not open an issue if you haven't checked the link and made sure your image was not corrupted yourself (you can use the workflow logs to see that)

Upload recovery.img (*not* recovery.img.lz4) to a file host website [like this](https://transfer.sh),  
go over to the `Actions` tab on your fork, select `Patch Image via URL` and click `Run Workflow`.  
Paste the file host link for your recovery image (e.g. https://transfer.sh/xxxxxx/recovery.img),  
Click `Run Workflow` again, and when it's done you should have 2 files available to download - 1 being the keys, of which signifigance I'm not sure myself, and the other will hold
your patched recovery image, and a version of it that you can use for odin.

#### Natively (Arch/Debian)
> Note: you're going to need the packages *(git, wget, lz4, tar, openssl, & python3)*,  
> and *recovery.img.lz4 or recovery.img.* Personally, I unzipped the AP archive of a stock rom and got my recovery image from that.

If you have those, then clone the repository, and move your recovery image to it.
```bash
git clone github.com/engineer4t/fastboot-patcher.git && mv recovery.img.lz4 ./fastboot-patcher/ && cd fastboot-patcher
```
Then, just simply run the script with this command and wait for it to finish, it shouldn't take longer than a minute.
```bash
chmod a+x ./magiskboot && chmod a+x ./patcher && ./patcher
```
You'll find the original recovery image and 2 new images *(.img and .tar.md5 for odin)* in the top directory if successful.
