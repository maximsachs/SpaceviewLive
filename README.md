 Spaceview Live
=============
 *Enjoy the view!*

Auto-updating photos of the Earth from 1.5 million Km away for your desktop wallpaper or screen saver.

![alt tag](https://raw.github.com/DavidMarzocca/SpaceviewLive/master/DSCOVR%20Wallpaper%20Example.png)

Introduction
--------------

The DSCOVR (Deep Space Climate Observatory) satellite is in the Lagrange point L1, approximately 1.5 million Km from Earth.
http://www.nesdis.noaa.gov/DSCOVR/
From this position it always sees the sun-illuminated side of the Earth.

High resolution photos from its EPIC (Earth Polychromatic Imaging Camera) camera are uploaded on http://epic.gsfc.nasa.gov/ every day, within 12 to 36 hours from the time they are taken. For each day there are about 10-14 photos: approximately one every two hours.

This script downloads the photo with the closest time to the present time of the day (within 2 hours), starting from the present day and going backwards until such a photo is found.
The photo is saved in the /photos/ folder (within the folder where the script is installed).
This can be used to create a desktop wallpaper which auto-updates with these photos:
an awesome Earth-looking window from a great vantage point in space.
It can also be used to create an awesome screen-saver.

Dependencies
----------------

The script needs:
> - Python (tested on v.2.7)
> - Crone

Both should come by default in all Unix systems (Linux and Mac).


Instructions for any Ubuntu 17.10
-----------

0. Put the files DSCOVR.py and install_shell.sh in a folder.

0. Access that folder with the terminal and run the shell script with:
   ```
   ./install_shell.sh
   ```
   A folder /photos/ is created (within the folder where the script is installed) and the photos are downloaded inside.
   Every 30 minutes the script will check for an update on the DSCOVR website.

0. From the terminal, the list of active crone jobs can be checked with the command `crontab -l`

0. Modify the DISCOVR script to point to the wallpaper folder of your username. Then open the Ubuntu 17.10 Settings and select DSCOVR.png in your wallpaper folder as background.

0. To scale the picture properly either install genome tweak utilities or use: gsettings set org.gnome.desktop.background picture-options "scaled"

Uninstall
-----------

0. Cancel all the files contained in the package.

0. To remove the automatic download open crone and cancel the line with the job.
    A good way to do this is write this in a terminal window:
    ```
   env EDITOR=nano crontab -e
   ```
	Cancel the job save the file by pressing Control + O, then Enter to accept and finally exit nano by pressing Control + X.
