# Big-B-Router  
### Offline Anti-ALPR routing and navigation for your phone.  

Ipynb to edit out ALPR exposed roads from PBF files. This can then be converted into an OBF file for use in [OsmAnd](https://osmand.net/).  

<img width="1648" height="762" alt="nav-example" src="https://github.com/user-attachments/assets/97df2186-bf89-4486-8e3d-cd605379f668" />  

## Finished OBF file demo  

[bigbrouter.webm](https://github.com/user-attachments/assets/72dcea2c-5c7c-4822-8a2c-ff9c2b7ca1ca)  

  
OsmAnd is available for iOS as well, although I have not tested.  

## Usage  
I wrote a step by step guide showing the whole process. [Link here](https://pickpj.github.io/Mapping/FIock/bigbrouter.html)  
  
TLDR:
- Download Requirements (env), pbf map data from [geofabrik](https://download.geofabrik.de/) or [other providers](https://wiki.openstreetmap.org/wiki/Planet.osm#Extracts)  
- Prep the pbf data with the pbf-prep.ipynb  
- Process the data with big-b-router.ipynb  
- Plug in the output to OsmAndMapCreator  
- Transfer OBF file to phone and import with OsmAnd  
  
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
### Updates 
I got maps working in Comaps, so its time to compare all the options.  
My recommendation is either:  
  
Osmand~ from F-Droid and mounting the phone (Osmand~ has extra features compared to the G-Play version)  
or   
The paid Osmand+ (G-Play) option if you need/want Android Auto  
  
Comparison matrix:  
Application [🟢Rec]| Free?| Navigation/Re-routing | Works offline | Android Auto| Easy?|   
---|---|---|---|---|---|  
Osmand (G-Play)|✅|✅|✅|❌|✅|  
🟢Osmand+ (G-Play)|❌<sup>1</sup>|✅|✅|✅|✅|  
🟢Osmand~ (F-Droid)|✅|✅|✅|🟠<sup>2</sup>|✅|  
Comaps (G-Play)|✅|✅|✅|✅|❌<sup>3</sup>|  
Comaps (F-Droid)|✅|✅|✅|🟠<sup>2</sup>|❌<sup>3</sup>|  

1. Osmand+ (Maps+) costs ~15$/year or 70$/once, giving AA/Carplay access (sometimes goes on sale)  
2. Have not done this, but it seems like it is possible to enable AA by pretending/faking the app is installed through G-Play. You most likely need a rooted device to use Kinginstaller   
3. Comaps uses a different mapgen in the comaps branch. Getting the [comaps repo](https://codeberg.org/comaps/comaps) setup for map conversion is difficult, but I have some tips that might help [link not here yet]  

---  
### Future Ideas:  
* Working on getting the mapgen to work with routing.xml files for weighted routing. The weights would also be togglable and adjustable within the driving profile. (this would only be for osmand)  

---
#### Credits  
* Impossible without OpenStreetMap data & contributors  
* pyosmium / osmium - nothing else worked for editing osm data and keeping/returning it as a pbf  
* OsmAnd and OsmAndMapCreator  
* pyrosm for reading pbfs to geopandas  
---  

![fIock](https://github.com/user-attachments/assets/ee47540e-ec21-40ce-b8b8-590d16af8e4b)

