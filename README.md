# Big-B-Router
Ipynb to edit out ALPR exposed roads from PBF files. This can then be converted into an OBF file for use in [OsmAnd](https://osmand.net/).  

## Finished OBF file demo
[bigbrouter.webm](https://github.com/user-attachments/assets/e8a99d25-e6ed-437e-9b82-5e7b6aa1a721)  


OsmAnd is available for iOS as well, although I have not tested. 

## Requirements  
### cli tool:  
- [osmium-tool](https://osmcode.org/osmium-tool/)
  -   [AUR link](https://aur.archlinux.org/packages/osmium-tool)

### python environment:  
- jupyter-notebooks
- ipyleaflet  
- geopandas  
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
