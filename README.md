# hackintosh-stuff

## Requirements
* Disable SIP

## Required kexts
* Whatevergreen
* LiLu

> Patches CoreDisplay Driver to enable 60Hz over DP-to-HDMI adapter

Copy the files from `kexts` to `/Library/Extensions`. Make sure to use a proper tool like `Hackintool` that fixes permissions and clears kext caches.

## Required boot arguments
Add boot arguments:

```
sudo nvram boot-args="kext-dev-mode=1 -cdfon -enable-hdmi20 -cdfbeta"
```

> Enables 4k 60Hz patches for Intel and NVidia (with web drivers)

## Tools
* FixEDID to transform EDID binary file to proper display overrides plist (only inject binary edid)
* AWEDIDEditor to edit the binary file and add proper display modes
* Hackintool to install kexts
* edid-decode to check patched edid binary files
* crscreen to switch to unsupported resolution:, eg. `cscreen -s 1 -f -x 3840 -y 2160 -r 60`