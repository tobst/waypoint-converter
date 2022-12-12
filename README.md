# waypoint-converter
Converts waypoints
This converter was started in order to generate Hyperlapse waypoint missions suitable for the Mini 3 Pro from DroneHarmony-csv files. Its work-in-progress, and has not been successfully tested yet.

## Usage
`python3 convert.py -h`

## Example
`python3 convert.py test-dh-legacy.csv -t 500 -s 3 -dh 5 -m 2 -p 45 -i -int 100 -dur 220`
This created a mission that was loaded successfully (RC firmware version 01.01.0300, Mini 3 Pro firmware 01.00.0300). It seems like the altitude depends on the gps altitude of the drone when starting, which can be off by several meters. `-s 3 -dh 5` creates 3 missions, separated by 5m each, starting at the specified altitude (500m, `-t 500`). 


## Transfer missions
### DJI RC
Copy the folders to an sd-card (preferably the one you use with the RC anyway). Insert sd-card into the RC. Swiping down you should be able to view the content of your sd-card and copy the files to something like "DJI RC/Android/data/dji.go.v5/files/Hyperlapse". Next time you fly, the copied missions should be visible in the Hyperlapse mode.

## Known issues
### Altitude 
Flight altitude is not set correctly as a MSL or similar. For now its try and error. You can create multiple missions with different offsets using `-s 5 -dh 2` to create 5 missions which have an offset of 2m in altitude each.

### Smooth Flighpaths
Hyperlapse waypoint missions on the Mini 3 pro are smoothed in order to achieve a smooth hyperlapse video. Thi smeans that the drone can and will leave the flight path. In tests this could be avoided by repeating the waypoints using `-m 2`


