# Disclaimer: Use at your own risk!
While this guide probably won't harm your device, I am not responsible for any damage or if anything goes wrong

# acer-nitro-power guide
A guide to enable NitroSense-like profiles without third-party programs, and manage them with tlp

# Tested and fully working on Acer Nitro ANV15-51 ✅
<img width="1021" height="590" alt="resim" src="https://github.com/user-attachments/assets/aedcc04e-d65c-4ebb-bc37-34432a27078a" />

# Introduction

NitroSense-like functionality already exists in the acer_wmi driver, but it isn't enabled by default.
If your hardware uses predator/nitrosense >=v4 on Windows, and you enable the "acer_wmi.predator_v4=1" kernel parameter, you can now monitor your fan speed and enable
platform profiles like quiet,balanced, etc. 
# Diagnostics

<img width="580" height="59" alt="resim" src="https://github.com/user-attachments/assets/b818c441-ddef-4a13-ac54-0dea4c18bd4b" />

My laptop has these platform profiles exposed. Low-power and quiet are pretty self-explanatory, balanced is balanced but I believe the balanced-performance profile is
the Performance mode on Windows as you cannot enable the performance platform profile on my laptop. I believe that corresponds to the Turbo mode that my laptop does not have. YMMV.

If you have Turbo mode and/or the performance platform profile works, you're done!
# For laptops without turbo mode and/or performance platform profile doesn't work

The issue after this is that when I try to enable performance mode using ppd or other similar software, I can't, since performance platform profile does not work on my laptop.
So you need to use tlp, and change these config lines accordingly, and then it should work.

<img width="438" height="62" alt="resim" src="https://github.com/user-attachments/assets/f6980f80-9216-4e9d-8523-055e8ff57336" />
