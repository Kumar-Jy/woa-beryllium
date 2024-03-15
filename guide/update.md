<img align="right" src="https://github.com/n00b69/woaberyllium/blob/main/beryllium.png" width="350" alt="Windows 11 running on beryllium">


# Running Windows on the Xiaomi Pocophone F1

## Updating Drivers

### Prerequisites


- [UEFI image](https://github.com/n00b69/woaberyllium/releases/tag/UEFI)

- [Recovery image]()

- [Drivers]()

### Start recovery through the PC with the command

```cmd
fastboot boot <recovery.img>
```


### Activate mass storage mode
> If it asks you to run it once again, do so
```cmd
adb shell msc
```

### Assign letters to disks

#### Start the Windows disk manager

> Once the Pad 5 is detected as a disk

```cmd
diskpart
```


### Assign `X` to Windows volume

#### Select the Windows volume of the tablet
> Use `list volume` to find it, it's the one named "WINNABU"

```diskpart
select volume <number>
```

#### Assign the letter X
```diskpart
assign letter x
```

### Exit diskpart
```diskpart
exit
```


### Install Drivers

> If it writes `"Automatic WINNABU detection failed! Enter Drive Letter manually"` type **`X`**
```cmd
 Open the folder with Drivers and run OfflineUpdater.cmd
```

### Reboot to fastboot to flash UEFI
> Or if your UEFI has already been flashed, simply reboot with ```adb reboot```
```cmd
adb reboot bootloader
```

#### Boot with Windows bootable UEFI image
> Replace <uefi.img> with the actual path of the UEFI image
```cmd
fastboot flash boot <uefi.img>
```

## Finished!









