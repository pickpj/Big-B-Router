# Big-B-Router  
### Offline Anti-ALPR routing and navigation for your phone.  

Ipynb to edit out ALPR exposed roads from PBF files. This can then be converted into an OBF file for use in [OsmAnd](https://osmand.net/).  

## Finished OBF file demo  
[bigbrouter.webm](https://github.com/user-attachments/assets/72dcea2c-5c7c-4822-8a2c-ff9c2b7ca1ca)  

  
OsmAnd is available for iOS as well, although I have not tested.  

## Requirements  
### cli tool:  
- [osmium-tool](https://osmcode.org/osmium-tool/)  
  -   [AUR link](https://aur.archlinux.org/packages/osmium-tool)  

### python environment:  
- jupyter-notebooks  
- geopandas  
- folium  
- pyrosm  
- pyosmium  

## Usage  
After downloading the Requirements,  
- Download pbf map data of the state from [geofabrik](https://download.geofabrik.de/) or from [other providers](https://wiki.openstreetmap.org/wiki/Planet.osm#Extracts)  
- Prep the pbf data with the pbf-prep.ipynb  
- Process the data with big-b-router.ipynb  
- Plug in the output to OsmAndMapCreator  
- Transfer OBF file to phone and import with OsmAnd  

### Potential improvement ideas  
- Mark roads as either [ice roads, 4WD roads, or low emission zones]; then the anti-ALPR routing could be toggled in OsmAnd route parameter settings to avoid or not avoid the road type (ie. on/off switch for ALPR avoidance).  
  - low emission zones are ways that define an outer boundary  
    - write all roads and let osmand handle LEZ's? (No low emission zones in the US that I could find)   
    - easier option? Looked at an LEZ in osm and did not see any nodes on road intersections. (no need to include nodes at intersections?)  
    - relation w/ boundary="low_emission_zone" write geoseries.exterior of alprtrap geometries as the member way of each LEZ to output file?
    - https://www.openstreetmap.org/relation/19100581#map=14/52.07998/4.30844      
  - ice roads, 4wd roads as highway tags ice_road, ford, winter_road?;  
    - write roads with tags, longer roads that are split would go about the same process, but with tags on the cropped section (use overlay how=intersection geometry in addition to difference?)  
- Add the ability to add obstacles that would be defined in the routing.xml to add x amount of time. The idea being that you would shrink the cone to remove roads, and have a larger area that would be disadvantaged by the "obstacle". Typically a close road would pick up the LP (license plate), but a further road may be perpendicular, which may pickup vehicle metadata which you would prefer to avoid (through time penalties), but not remove.  
  
---
#### Credits  
* Impossible without OpenStreetMap data & contributors  
* pyosmium / osmium - nothing else worked for editing osm data and keeping/returning it as a pbf  
* OsmAnd and OsmAndMapCreator  
* pyrosm for reading pbfs to geopandas  
---  

![fIock](https://github.com/user-attachments/assets/ee47540e-ec21-40ce-b8b8-590d16af8e4b)

