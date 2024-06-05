# Soundbath 2.1
Soundbath is a data sonification of live rainfall data from England, Scotland, and Wales. The data updates every 15 minutes and is sonified using an RNBO web export. The max patch containing the RNBO module is contained within.

The project takes real-time data from:
Department for Environment Food & Rural Affairs’ Rainfall API data API:
https://environment.data.gov.uk/flood-monitoring/doc/rainfall

Natural Resources Wales:
https://api-portal.naturalresources.wales/api-details#api=open-data-river-level-rainfall
-and-sea-data-api&operation=historicaldataforstationparameter

SEPA(Scotland):
https://www2.sepa.org.uk/rainfall/DataDownload
  
The page is currently hosted as a GitHub Page:
https://finnheathfield.github.io/Soundbath-2.1/

The original version of this project was a collaboration between myself, Anna Dowell, Lauren Scott, and Imran Muhammed. The original repo can be found here: https://github.com/annadowell/soundbath2

This version has been slightly debugged for stability and has an updated RNBO patch to better aid functionality.

# Running Max Patch Locally
The supplied Max Patch allows for the RNBO device to be explored and run locally. To run correctly, you must also download the foley WAV file within this repo, located at soundbath-2.1/export/media/walesfoley.wav 
You then need to give the buffer object within RNBO the location the wav is stored on your machine. The correct placement is as such:
Replace "@file /Users/finnheathfield/Desktop/Tech/Year_2/Term_2/Rain_Sonification/Foley/walesfoley.wav" with "@file /filepathhere/walesfoley.wav"
The buffer is located by entering sub patches as follows:
FullRebuild (RNBO Patch) -> p Rainfall Effect -> p @title RainEffects @polyphony 64 ... -> buffer~ @name Foley1
