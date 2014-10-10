---
layout: doc
title: SoundProperties
collection: api
category: Audio
---

## downloaded
Type: boolean
Description: If the audiofile has been downloaded from the internet, return true. Else, return false.

Example: 

```
var soundURL = "https://s3.amazonaws.com/hifi-public/sounds/FamilyStereo.raw";
var audioOptions = new AudioInjectionOptions();
audioOptions.isStereo = true;
audioOptions.position = MyAvatar.position;
var sound = new Sound(soundURL, audioOptions.isStereo);

//check if sound has been downloaded
if (sound.downloaded) {
print("Sound file downloaded");
}
```