# Extract-Vendor-Blobs
A guide on how to extract vendor blobs and update your vendor tree blobs from stock ROM

# Android Vendor Trees Collection
- Vendor Blobs are purely based on proprietary-list.txt included in the Device Tree used in extracting.
- It maybe edited or not edited.
- Device and Vendor Names might different from what the device itself says.
    - So I will be putting the Device Name in the Description Area just to be clear.
- If you want to request, submit an [issue](https://github.com/Vendor-Blobs/.github/issues).
    - As long as theres existing Device Tree and Android Dump for that specific device, I'll do it.
    
Note: The gitLab instance where I usually get android dump, not working anymore. So I will be using other repo site or instance as my source.


## Credits:
- [Dumpyara](https://github.com/sebaubuntu-python/dumpyara)
- [Aospdtgen](https://github.com/sebaubuntu-python/aospdtgen)
- [DumprX](https://github.com/DumprX/DumprX)
- [AndroidDump](https://github.com/AndroidDumps/dumpyara)
- LineageOS
    - [Extract-Tools](https://github.com/LineageOS/android_prebuilts_extract-tools)
    - [Extract-Utils](https://github.com/LineageOS/android_tools_extract-utils)
    
## Guide to Extract Vendor Blobs from Android Dump
- Dump a Firmware using dumping tool/script of your choice like Dumpyara, DumprX..etc.
- Change directory to the rom source
- Clone neccessary tools/scripts inside the rom source directory - most lineage based roms have these two repos cloned already:
```
     git clone https://github.com/LineageOS/android_tools_extract-utils -b lineage-22.1 android/tools/extract-utils
     git clone https://github.com/LineageOS/android_prebuilts_extract-tools -b lineage-22.1 android/prebuilts/extract-tools
```
 - Clone or Copy/Move your Existing Device Tree inside rom_source/device/vendorname/codename directory if not already cloned.
    - If you don't have yet, use aosptdtgen to generate device tree.
 - Directory should be look like this:
 ```
    - rom_source/
        - device/
            - vendorname/
                - devicecodename/
        - android/
            - tools/
                - extract-utils/
            - prebuilts/
                - extract-tools/
  ```
  - Inside you device tree folder, run:
  ```
  bash extract-files.sh /path/directory/to/your/rom_dump/
  ```
  - Wait until finished. You'll find the blobs under android/vendor/vendorname/codename
    
