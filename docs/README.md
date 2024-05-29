# PostGIS
> Application: Shortest Route Using pgRouting Using PostgreSQL, pgRouting & QGIS

## pgRouting

`pgRouting` extends the PostGIS / PostgreSQL geospatial database to provide geospatial routing functionality. 

Official `pgRouting` Website: https://pgrouting.org/


## Installation and Setting Up 
### Pre-requisities for this application:

| S.N. | Software   | Link |
| ---- | ---------- | ----- |
| 1.   | PostgreSQL | https://www.postgresql.org/download/ |
| 2.   | PostGIS    | https://postgis.net/documentation/getting_started/install_windows/|
| 3.   | pgRouting  | Included with PostGIS Package      |
| 4.   |QGIS        | https://www.qgis.org/en/site/forusers/download.html   |
| 5.   |osm2po      | https://osm2po.de/releases/    |
| 6.   |JAVA        | https://www.java.com/en/download/    |

> 1. PostgreSQL

The installation of PostgreSQL is pretty straightforward and can be downloaded from the Link provided above.

> 2. PostGIS

PostGIS is a spatial extension for PostgreSQL. It can be installed using the link provided above. Also, After installing PostgreSQl on your system, PostGIS can be installed using Stack Builder Application.

> 3. pgRouting

It is included with the PostGIS bundle.

> 4. QGIS

This Open-Source GIS applicaton can be downloaded with the link provided above.

> 5. osm2po

The osm2po package can be downloaded from the link provided above. This package takes as input the raw OSM data (eg. .PBF format) and converts the data into a SQL file which can be imported into our Spatial Database and used for the pgRouting implementation. The following steps can be followed for the installation of osm2po.  
* Visit: `https://osm2po.de/`
* Download: `osm2po-5.5.11`  

![osm2po website](/images/osm2po_website.png "osm2po Website")

* Extract files from: `osm2po-5.5.11`

![osm2po file extract](/images/osm2po_windowsexplorer.png "osm2po Website")

* Open: osm2po.config using Notepad  

![osm2po config file select](/images/osm2po_configfileselect.png "osm2po Website")

* Edit Line 179: wtr.finalMask = car,foot,bike  

![osm2po config file edit 1](/images/osm2po_configfileedit1.png "osm2po Website")

* Edit Line 330: Remove # in the beginning  

![osm2po config file edit 2](/images/osm2po_configfileedit2.png "osm2po Website")

* Save the file.

> 6. JAVA  

* Go to: https://www.java.com/download/ie_manual.jsp  

* Install Java:  

![java install](/images/java_install.png "java install")
 
* Note: If java is not installed, it shows something like this on Command Prompt.  

![java install error](/images/java_notinstallederror.png "java install")

* Note: If java is installed successfully, it shows something like this on Command Prompt.

![java install](/images/java_installationsuccessful.png "java install")


## Downloading OSM Data:  
* Go to: https://download.geofabrik.de/asia.html  

* Download OSM Data in .PBF format (I am downloading data for Nepal)  

![OSM Data Download](/images/osm_datadownload.png "OSM Data Download")

## Pre-processing OSM Data in osm2po:  
* Open Command Prompt: Type the following command
![OSM Data Preprocessing](/images/osm2po_preprocessing.png "OSM Data Preprocessing")

* Navigate to the converted file.
![Converted File Navigation](/images/converted_file_command_prompt.png "Converted File Navigation")

* Navigate to the converted file in Windows Explorer.

![OSM Data Preprocessing](/images/converted_file_windows_explorer.png "OSM Data Preprocessing")

## pgAdmin:  

* Create Database pgrouting

* Run: Create Extension postgis
![postgis_extension](/images/postgis_extension.png "postgis_extension")

* Run: Create Extension pgrouting
![pgrouting_extension](/images/pgrouting_extension.png "pgrouting_extension")

* Open: .sql file Converted earlier

![sql_file](/images/sql_file.png "sql_file")

* Execute

* Simple Query and Output  

![simpleoutput](/images/simpleoutput.png "simpleoutput")

* Simple Query and Output on Geometry Viewer
![geometry_viewer](/images/geometry_viewer.png "geometry_viewer")

## Origin and Destination:
+ For this, I have Selected Kalanki (27.6932983, 85.2816525) as the Origin and Nagarkot( 27.6920550, 85.5199997) as the destination.

## QGIS:

Origin: Kalanki (27.6932983, 85.2816525) 

![start_point_1](/images/start_point_1.png "start_point_1")

The Origin(Starting Point/Nearest node) is indicated by green dots.

![start_point_2](/images/start_point_2.png "start_point_2")

Destination : Nagarkot (27.6920550, 85.5199997)

![end_point_1](/images/end_point_1.png "end_point_1")

The Destination(End Point/Nearest node) is indicated by blacks dots.

![end_point_2](/images/end_point_2.png "end_point_2")

* Finally, the overall Query for Shortest Route:

![final_query](/images/final_query.png "final_query")

* All three layers, Origin, Destination and Shortest Route added as new layer in QGIS.

![final_result](/images/final_result.png "final_result")

> This concludes this one simple demonstration of determining the shortest route using `pgRouting`.

