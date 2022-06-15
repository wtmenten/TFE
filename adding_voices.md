# Adding new bot voices guide

Due to how the asset files are linked with map ID's 
adding new .bundle files won't let us link into the voice collection in assets/content/phrases/allphrases.bundle


We can however add new voice into the existing files, by duplicating the existing MonoBehaviors and AudioClips.

This is actually how alot of the voice code used to be arranged in 12.9


- first pick a pathID range to use eg. 1337<random_digits>
  - loaded up all the asset files in assetstudio and sort by path to find a free range.

- add voice to collection: `assets/content/phrases/allphrases.bundle` 
  - Use a known fileID by mapping the pathID of the voice control asset `Scav_#_Voice` below with the `AllPhrases.Voices.m_PathID`
      - eg. FID 4 in Allphrases -> scav 1
- 
- voice controls in: assets/content/phrases/scav_#_voice.bundle 
  - file ids
    - 1 = default voice file `assets/content/voice/scav/scav#.bundle`
- voice file: assets/content/voice/scav/scav#.bundle
    - add audio clips here

At this point you should have 
duplicated the audio files, 
the audio control behaviors 
and added the new controller to the allphrases voice collection

The voice should now be available via the name in the voice controller you made