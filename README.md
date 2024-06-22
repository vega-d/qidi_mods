# qidi_mods
a set of mods to qidi printers. Assorted by model.

Each of the folders contains a printer.cfg, originally published by Qidi Tech, but modified by yours truly.

The changes I have done to printer.cfg files:
- speed up homing (40mm/s => 100mm/s)
- alter sensitivity during homing, homes with less noise
- use back left corner of the movement envelope
- alter Z homing for faster movement


## if you have not modified your printer.cfg
to apply this mod:
- download the printer.cfg for your printer (click green code button, download as zip, extract).
- connect your printer to your local network (wifi/ethernet).
- open Fluidd web interface of the printer.
- navigate to the configuration category.
- delete the existing printer.cfg file (right click).
- click upload, and select the printer.cfg for your printer out a folder you unzipped this project into.
- reboot the printer.
- home the printer, hover your finger over the red stop button for the first time in case it fails.
- if it didn't fail, you have now modded your printer into being a slightly better printer!
- if it does fail, please open a ticket under the issues tab of this repository. 

## if you HAVE modified your printer.cfg before
- you know what you're doing. Proceed. 
- if you do not know what you're doing, ask someone who does. You can reach out to me by email at msg@vega76.cz

## what is this ominous .tar.gz file in the repo?
I took the stock klipper install out of my x plus 3 and put it in a tarball.
On an offchance you accidentally clicked "update" in the fluidd webui of stock firmware and soft-bricked the printer, this is what y>
this command should extract the klipper install into a temp folder, wipe your existing one, and move my backup copy in place. then c>
```
cd /tmp && \
git clone https://github.com/vega-d/qidi_mods && \
tar -zxvf qidi_mods/stock-klipper.tar.gz -C /tmp/ && \
rm -rf /home/mks/klipper && \
mv -r /tmp/mnt/stockfw/home/mks/klipper /home/mks/
```

# credits:
- Thanks to https://github.com/DaNinjaSmurf for beta testing this on X plus 3
- Thanks to `argueforsport` on discord for providing measurements for X max 3
