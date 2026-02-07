# Falcon Brief

A lightweight utility that converts DTC and Briefing data into Kneeboard pages. In addition to briefing it also includes map pages for reference and customized checklists, pdf and images. This product is meant to be used with Falcon 4.38.

## Limitations: 
- Due to BMS not adding all steerpoints inside DTC files but rather just a subset, bullseye stpt is not present. In order to overcome this limitation the user must set the last PPT above the bullseye and set "BRAVO" as label. This will hint the software to where the bullseye is located. 
- Fuel plan is very conservative
- Airports runway ILS are WIP

## Left Kneeboard Default Pages:
- Package & Support
- Pilot Roster & Comms Ladder
- Special Instructions (threats, roe, and emergency procedures)
- IFF
- Link 16
- Ordnance
- Fuel, Flight Plan & Targets
- Threats Tables
- Airport (departure, arrival, alternate)

## Right Kneeboard Default Pages:
- Normal Checklist
- Emergency Procedure Checklist
- Bulleye Situation Reference Map
- Flight Path Reference Map
- Engagement Zone Reference Map
- CAS
- Notes

## How to use?
Once the user is satisfied with the mission params (loadout, paths, ppt and lines) the user must ensure that the last ppt matches the bullseye location and is set to BRAVO. Then the user clicks print briefing (which must be set to output as text) and then clicks save DTC. For last but not least the user run the application FalconBrief.exe and after this operation the software will save the output in "Documents\FalconBrief\output".  

Adding custom checklist, images or PDF is supported. This is done by replicating the following filesystem:

Documents
|- FalconBrief
   |- custom
      |- left
         |- common
         |- {platform}
         |- {platform+variation}
      |- right
         |- common
         |- {platform}
         |- {platform+variation}

Rendering rules:
- common, are always rendered
- {platform} (es. F-16, F-15), are rendered only when the player aircraft platform matches
- {platform+variation} (es. F-16C, F-15C), are rendered only when the player aircraft platform and variation matches.

In addition to custom pages, config.ini located in Documents\FalconBrief allow further fine tunes:
- GenerateDDS, 0 or 1. Generate DDS and swap with default textures
- HighContrastMap, 0 or 1. Use colorized or high contrast image for map
- LeftPages, 0 ... N comma separeted list. Indicated which page to generate and the order for left kneeboard
- RightPages, 0 ... N comma separeted list. Indicated which page to generate and the order for right kneeboard
- UnifiedPages, 0 ... N comma separeted list. Indicated which page to generate and the order for unified kneeboard

Page Codes:
0 = MissionData
1 = Commns
2 = SPINS
3 = IFF
4 = Link16
5 = Loadout
6 = WaypointAndTargets
7 = ThreatsTable
8 = Airports  
9 = StationsList  
10 = LExtraCommon
11 = LExtraPlatform
12 = LExtraVariation
13 = NormalChecklist
14 = EmergencyChecklist
15 = BulleyeMap
16 = FlightPathMap
17 = EngagementZoneMap
18 = CAS
19 = Notes
20 = RExtraCommon
21 = RExtraPlatform
22 = RExtraVariation
