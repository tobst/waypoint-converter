# waypoint-converter
Converts waypoints
This converter was started in order to generate Hyperlapse waypoint missions suitable for the Mini 3 Pro from DroneHarmony-csv files. Its work-in-progress, and has not been successfully tested yet.

## Usage
`python3 convert.py -h`

## Known issues
### Altitude 
Flight altitude is not set correctly as a MSL or similar. For now its try and error. You can create multiple missions with different offsets using `-s 5 -dh 2` to create 5 missions which have an offset of 2m in altitude each.

### Smooth Flighpaths
Hyperlapse waypoint missions on the Mini 3 pro are smoothed in order to achieve a smooth hyperlapse video. Thi smeans that the drone can and will leave the flight path. In tests this could be avoided by repeating the waypoints using `-m 2`


