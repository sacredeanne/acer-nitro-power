# Disclaimer: Use at your own risk!
While this guide probably won't harm your device, I am not responsible for any damage or if anything goes wrong

# acer-nitro-power guide
A guide to enable NitroSense-like profiles without third-party programs

# Tested and fully working on Acer Nitro ANV15-51 ✅
<img width="1021" height="590" alt="resim" src="https://github.com/user-attachments/assets/aedcc04e-d65c-4ebb-bc37-34432a27078a" />
<img width="1057" height="691" alt="resim" src="https://github.com/user-attachments/assets/8df6bc36-e03f-42ea-aaea-709fdf83644b" />

# TL;DR
--- If you have a laptop without Turbo Mode ---

1-) Enable the "acer_wmi.predator_v4=1" kernel parameter. If you use grub you can do this on most distros by modifying /etc/default/grub (GRUB_CMDLINE_LINUX_DEFAULT="acer_wmi.predator_v4=1") and updating the grub config file (update-grub, grub-mkconfig -o /boot/grub/grub.cfg, etc.).

If you don't use grub, look at your bootloader's documentation on how to do so.

2-) Install tlp and tlp-pd

3-) Use the tlp.conf that I provided.

4-) Done! power-saver profile will use low-power platform profile and limit cpu to 60%, balanced will be balanced mode and performance mode will use balanced-performance (performance mode on windows).

--- If you have a laptop *with* Turbo Mode ---

1-) Enable the "acer_wmi.predator_v4=1" kernel parameter. If you use grub you can do this on most distros by modifying /etc/default/grub (GRUB_CMDLINE_LINUX_DEFAULT="acer_wmi.predator_v4=1") and updating the grub config file (update-grub, grub-mkconfig -o /boot/grub/grub.cfg, etc.).

If you don't use grub, look at your bootloader's documentation on how to do so.

2-) Use power-profiles-daemon or tlp

3-) Done!

# For people who are curious
NitroSense-like functionality already exists in the acer_wmi driver, but it isn't enabled by default.
If your hardware uses predator/nitrosense >=v4 on Windows, and you enable the "acer_wmi.predator_v4=1" kernel parameter, you can now monitor your fan speed and enable
platform profiles like quiet,balanced, etc.

<img width="580" height="59" alt="resim" src="https://github.com/user-attachments/assets/b818c441-ddef-4a13-ac54-0dea4c18bd4b" />

My laptop has these platform profiles exposed. Low-power and quiet are pretty self-explanatory, balanced is balanced but I believe the balanced-performance profile is
the Performance mode on Windows as you cannot enable the performance platform profile on my laptop. I think performance platform profile corresponds to the Turbo mode that my laptop does not have.

The issue after this is that when I try to enable performance mode using ppd or other similar software, I can't, since performance platform profile does not work on my laptop.
So you need to use tlp, and change the "PLATFORM_PROFILE_ON_AC" config line accordingly, and then it should work.

<img width="438" height="62" alt="resim" src="https://github.com/user-attachments/assets/f6980f80-9216-4e9d-8523-055e8ff57336" />

# Credits
https://wiki.archlinux.org/title/Laptop/Acer#Mode_key_and_fan_speed_monitoring_are_not_working_for_some_gaming_laptops and the amazing Linux kernel and acer_wmi developers
