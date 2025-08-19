# XY-table
automated XY stage that will be developed to make markings, laser-marks, laser-cuts, milling and 3D printing 
**Table of content:**
- [Goal](#goal)
- [Requirements](#requirements)
- [Development](#dev)
- [Engineering](#eng)
- [Parts & costs](#parts)
- [Product](#prod)
- [CNC3018 installation and use](#3018)

<!-- headings -->
<a id="goal"></a>
## Introduction and goal
For many DIY projects automated 2D and 3D modifications on materials are useful. For example:
* Markings for assembly and manual machining
* Markings for esthetics (artwork, UI)
* Cutting of sheet materials
* Milling of (small) metal objects
* 3D printing of small and medium sized plastics

All these modifications require at least a XY translation, and some also a Z translation. However, the required torque, speed and precision for the different applications varies a lot. In oder to design a product that is upto the task for all applications the extremes of each application has to be defined, and research is needed to make choices regarding feasibility and cost. In the section [Requirements](#requirements) a study of requirements for each application is made. In the [development](#dev) sections the platform development and sub-unit developments are described. In later stages [Engineering](#eng) sections will be added for the mechanical, electrical and systems & control designs of various parts. And finally the [product](#prod) section will describe the final product.

<a id="requirements"></a>
## Requirements
In this section requirements for various applications are investigated. Some of these requirements will lead to design criteria, which will be __marked__ in the text, and listed here.
__Design criteria__
* [Width](#DC-width): 1300mm
* [Length](#DC-length): 650mm
* [Feedthrough](#DC-feedthrough): plate material longer then 650mm can manually be feedthrough the length side of the platform
* [Feedthrough-height](#DC-feedthrough-height): 45mm


### Materials
Plate material readily available at the building depot (Hornbach) has dimensions of 4000, 3000, 2500, 2440, 2150, 2000, 1250, 1220 and 610mm. Most combinations can be made with materials that are 1250mm on one side. Therefore, the width of the platform will be a bit more then 1250mm: __1300mm__.<a id="DC-width"></a>
To fit the smallest common width of plate material the length of the platform will a bit larger then 610mm: __650mm__.<a id="DC-length"></a> Also, this side of the platform must allow __manual feedthrough__ for when materials with a width larger then 650mm are used.<a id="DC-feedthrough"></a>
The maximum available thickness of plate material is 40mm. Adding 5mm results in a __feedthrough height of 45mm__.<a id="DC-feedghrough-height"></a>

### Marking
Description

<a id="dev"></a>
## Development
- [Platform](#dev-platform)
- [Milling](#dev-milling)
- [Control](#dev-control)

<a id="dev-platform"></a>
### Platform development
Description

<a id="dev-milling"></a>
### Milling function development
Description
Second item content goes here

<a id="dev-control"></a>
### Control function development
- Use a Arduino with CNC shield to control up to four steppers
- Program GRBL on the arduino to run gcode from external source (laptop)
- Use UGS to interface between Arduino-GRBL and laptop
- Use EstlCAM to convert 3D model to gcode sequency (https://www.youtube.com/watch?v=xw0ZFf75lAM https://www.cnc-step.nl/cnc-software-cad-cam-frezen-software/estlcam/)
- Use OpenSCAD or FreeCAD for 3D model design

<a id="eng"></a>
## Engineering

- [Stage design](#eng-stage)
- [XY translation](#eng-XY)
- [Z translation](#eng-Z)

<a id="eng-stage"></a>
### Stage design
Description

<a id="eng-XY"></a>
### XY translation
Description

<a id="eng-Z"></a>
### Z translation
Description

<a id="parts"></a>
## Parts & costs

In this section an overview of parts, where to buy them, and cost is given.

| Part          | Store         | Price (€)|
| ------------- |:-------------:| --------:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

<a id="prod"></a>
## Final product

<a id="3018"></a>
## Kant en klare CNC tafel met 500W freeskop en 5.5W UV laser

De volgende stappen zijn genomen om deze te installeren
* Universal GCode sender software: https://winder.github.io/ugs_website/download/
* Vooraf ingestelde homing sequence van versie 2.1.8 werkt direct. Wel eerst x,y & z as buiten bereik van de eindschakelaar zetten.
* Firmware bestand opgeslagen op .git
Laser (https://docs.sainsmart.com/article/wzvu9798tc-genmitsu-3018-pro-5-5-w-laser-module-user-guide)
* Aansturing xyz werkt met ugs, maar laser aansturing niet standaard. Het is mogelijk om macro's aan te maken.
* sainsmart raad lasergrbl aan (https://lasergrbl.com/download/). Hieruit kunnen macro codes gekopieerd worden na importeren custom buttons

3D model naar gcode programma
* grijswaardes naar diepte en gcode (https://www.scorchworks.com/Dmap2gcode/dmap2gcode.html)
* gcode toolpath simulatie (https://camotics.org/download.html)

Gcode list
* https://www.machinistguides.com/g-codes/
* https://github.com/gnea/grbl/wiki/Grbl-v1.1-Commands
* werkt niet met CNC3018: G41 G42 G03 H08
