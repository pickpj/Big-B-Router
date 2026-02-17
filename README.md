# Big-B-Router
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

---
#### Credits  
* Impossible without OpenStreetMap data & contributors  
* pyosmium / osmium - nothing else worked for editing osm data and keeping/returning it as a pbf  
* OsmAnd and OsmAndMapCreator  
* pyrosm for reading pbfs to geopandas  
---  

![fIock](https://github.com/user-attachments/assets/ee47540e-ec21-40ce-b8b8-590d16af8e4b)

