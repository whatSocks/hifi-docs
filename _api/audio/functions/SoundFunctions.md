---
layout: doc
title: SoundFunctions
collection: api
category: Audio
developer: true
---

## Sound Sound(string soundURL, boolean isStereo)

Initialize a Sound object with a string URL to a sound file (a .wav file or a 16bit pcm 48k .raw file) and boolean stereo settings (`isSterero`). This downloads the file to the object and formats it appropriately. `Sound` objects can then be passed to `AudioInjectors` for use. 

## Example: 

```
var soundURL = "https://s3.amazonaws.com/hifi-public/sounds/FamilyStereo.raw";
var options = new AudioInjectionOptions();
options.isStereo = true;

//Creating the Sound
var sound = new Sound(soundURL, options.isStereo);

//verify that the sound has been downloaded
if (sound.downloaded) {
  print("Sound file downloaded");
  //playing the sound via an AudioInjector
  Audio.playSound(sound, options);
}
```
