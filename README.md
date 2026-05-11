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
  -   [conda forge](https://anaconda.org/conda-forge/osmium-tool)  
  
### python environment:  
- notebook  
- geopandas  
- folium  
- pyrosm  
- pyosmium  
- ipyleaflet  

Tested with `conda create -n gis-py312 -c conda-forge geopandas folium pyrosm pyosmium notebook ipyleaflet osmium-tool`  

## Usage  
After downloading the Requirements,  
- Download pbf map data of the state from [geofabrik](https://download.geofabrik.de/) or from [other providers](https://wiki.openstreetmap.org/wiki/Planet.osm#Extracts)  
- Prep the pbf data with the pbf-prep.ipynb  
- Process the data with big-b-router.ipynb  
- Plug in the output to OsmAndMapCreator  
- Transfer OBF file to phone and import with OsmAnd  
  
---
### Updates  
(Failed) Attempts at trying to simplify the process / separate it from road data (Trying to make it easier to use and to make files easier/smaller for distribution)  

Method| Separate File from Map| Merge w/ map -> osmandmapcreator |  
---|---|---|
Low Emission Zones|❌|🟠<sup>1</sup>|    
Barrier<sup>2</sup> Gates / Wall / Access=no|❌|❌|  
Barrier<sup>3</sup> Border Control|❌|❌|  

1. Converting to Obf seems to add data to the nodes that are contained within low emission zones. Then avoiding LEZ's would prevent crossing said nodes. The problem is that a projection may cross the way, but not a node (fairly common| roads have a tendency to be straight lines). So a different projection needs to be used, but I'm unsure if it's possible to do without interfering with the nodes in adjacent roads.  
2. Barriers although non functional for routing could be an easy way to overlay alpr location data on the map in osmand.
3. Barrier nodes are referenced by the way they sit on, it may be possible to integrate through a changeset.
---  
### Future Ideas:  
* Create procedure for comaps (seems possible to import custom maps)  
* Method: Changeset of all roads that is then applied to a map -> osmandmapcreator  

---
#### Credits  
* Impossible without OpenStreetMap data & contributors  
* pyosmium / osmium - nothing else worked for editing osm data and keeping/returning it as a pbf  
* OsmAnd and OsmAndMapCreator  
* pyrosm for reading pbfs to geopandas  
---  

![fIock](https://github.com/user-attachments/assets/ee47540e-ec21-40ce-b8b8-590d16af8e4b)

