# Disclaimer: Use at your own risk!
While this guide probably won't harm your device, I am not responsible for any damage or if anything goes wrong

# acer-nitro-power guide
A guide to enable NitroSense-like profiles without third-party programs

# Tested and fully working on Acer Nitro ANV15-51 ✅
<img width="1021" height="590" alt="resim" src="https://github.com/user-attachments/assets/aedcc04e-d65c-4ebb-bc37-34432a27078a" />

# TL;DR
If you have a laptop that doesn't support Turbo Mode on NitroSense, and your laptop is using NitroSense/PredatorSense >=v4 (like ANV15-51),
you can use the tlp.conf that I provided in this repo. FYI powersave mode will trigger low-power platform profile, balanced will use quiet,
and performance mode will use the balanced-performance platform profile.
While I can't vouch for it, I believe that if your laptop supports Turbo Mode and you use default tlp or ppd (power-profiles-daemon),
powersave will be low-power, balanced will be balanced, and performance mode will use the performance (Turbo) platform profile.

# Introduction

NitroSense-like functionality already exists in the acer_wmi driver, but it isn't enabled by default.
If your hardware uses predator/nitrosense >=v4 on Windows, and you enable the "acer_wmi.predator_v4=1" kernel parameter, you can now monitor your fan speed and enable
platform profiles like quiet,balanced, etc. 

# Diagnostics

<img width="580" height="59" alt="resim" src="https://github.com/user-attachments/assets/b818c441-ddef-4a13-ac54-0dea4c18bd4b" />

My laptop has these platform profiles exposed. Low-power and quiet are pretty self-explanatory, balanced is balanced but I believe the balanced-performance profile is
the Performance mode on Windows as you cannot enable the performance platform profile on my laptop. I think performance platform profile corresponds to the Turbo mode that my laptop does not have. YMMV.

If you have Turbo mode and/or the performance platform profile works, you're done!

# For laptops without turbo mode and/or performance platform profile doesn't work

The issue after this is that when I try to enable performance mode using ppd or other similar software, I can't, since performance platform profile does not work on my laptop.
So you need to use tlp, and change the "PLATFORM_PROFILE_ON_AC" config line accordingly, and then it should work.

<img width="438" height="62" alt="resim" src="https://github.com/user-attachments/assets/f6980f80-9216-4e9d-8523-055e8ff57336" />



# Credits
https://wiki.archlinux.org/title/Laptop/Acer#Mode_key_and_fan_speed_monitoring_are_not_working_for_some_gaming_laptops and the amazing Linux kernel and acer_wmi developers
