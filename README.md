# Big-B-Comaps  
### Offline Anti-ALPR routing and navigation for your phone.  

Ipynb to edit out ALPR exposed roads from PBF files. This can then be converted into an mwm file for use in [Comaps](https://www.comaps.app/).  
Compared to the Osmand example Comaps has Android Auto support for free.
The tradeoff is that this is a fair bit more complicated to set up than the Osmand example.  
Also the generated map differs slightly from the map generated for osmand, but should function similarly.  
  
If you want Android Auto for Osmand your option are to either: pay ~80$ for lifetime subscription to osmand+, ~8$/yr for maps+, or with a rooted android device figure out how to get osmand* from F-Droid to work with Android Auto.  
  

## Usage  
  
- Download Requirements (env), pbf map data from [geofabrik](https://download.geofabrik.de/) or [other providers](https://wiki.openstreetmap.org/wiki/Planet.osm#Extracts)  
- Prep the pbf data with the pbf-prep.ipynb  
- Process the data with big-b-comaps.ipynb  

- Generate mwm through the comaps repo (hard).  


## Requirements  
Tested with `conda create -n gis-py312 -c conda-forge geopandas folium pyrosm pyosmium notebook ipyleaflet osmium-tool`  
### cli tool:  
- [osmium-tool](https://osmcode.org/osmium-tool/)  
  -   [AUR link](https://aur.archlinux.org/packages/osmium-tool)  
  -   [conda forge](https://anaconda.org/conda-forge/osmium-tool)  
### python env:  
- notebook  
- geopandas  
- folium  
- pyrosm  
- pyosmium  
- ipyleaflet  


---
#### Credits  
* Impossible without OpenStreetMap data & contributors  
* pyosmium / osmium - nothing else worked for editing osm data and keeping/returning it as a pbf  
* OsmAnd and OsmAndMapCreator  
* pyrosm for reading pbfs to geopandas  
---  

![fIock](https://github.com/user-attachments/assets/ee47540e-ec21-40ce-b8b8-590d16af8e4b)

