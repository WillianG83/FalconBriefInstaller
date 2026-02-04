# Falcon Brief

A lightweight utility that converts DTC and Briefing data into Kneeboard pages. In addition to briefing it also includes map pages for reference and customized checklists, pdf and images. This product is meant to be used with Falcon 4.38.

## Limitations: 
- Due to BMS not adding all steerpoints inside DTC files but rather just a subset, bullseye stpt is not present. In order to overcome this limitation the user must set the last PPT above the bullseye and set "BRAVO" as label. This will hit the software to where the bullseye is located. 
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
Once the user is satisfied with the mission params (loadout, paths, ppt and lines) the user must ensure that the last ppt matches the bullseye location and is set to BRAVO. Then the user clicks print briefing (which must be set to output as text) and then clicks save DTC. After this operation the software will save the output in "Documents\FalconBrief\output".  

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

Obviously left and right distinction indicates where the custom file will be rendered. Rendering rules:
- common, are always rendered
- {platform} (es. F-16, F-15), are rendered only when the player aircraft platform matches
- {platform+variation} (es. F-16C, F-15C), are rendered only when the player aircraft platform and variation matches.

Custom files are always rendered after the default pages. 