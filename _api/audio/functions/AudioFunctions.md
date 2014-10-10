---
layout: doc
title: AudioFunctions
collection: api
category: Audio
developer: true
---

## bool isInjectorPlaying(AudioInjector injector)
Description: `isInjectorPlaying` returns a boolean value describing the play status of a given AudioInjector. 

## Example:

Take a look at this snippet of `playSoundLoop.js`:

```
  
        //starting the sound
        soundPlaying = Audio.playSound(sound, options);
        print("Started sound looping.");
        Script.update.disconnect(maybePlaySound);
    }
}
        
function scriptEnding() { 

    //if the injector is playing a sound, Audio.isInjectorPlaying(soundPlaying) returns `true`
    if (Audio.isInjectorPlaying(soundPlaying)) {
        Audio.stopInjector(soundPlaying);
        Entities.deleteEntity(ball);
        print("Stopped sound.");
    }

```

## AudioInjector playSound(Sound _sound_, AudioInjectorOptions _injectorOptions_)

`playSound` takes a `Sound` object and an `AudioInjectorOptions` object as inputs, returns an `AudioInjector` object, and initiates the playback of the intended `Sound` with the given options.

## Example:

Take a look at this snippet of `playSoundLoop.js`:

```
Script.include("libraries/globals.js");

//loading the URL into the Sound object
var sound = new Sound(HIFI_PUBLIC_BUCKET + "sounds/Guitars/Guitar+-+Nylon+A.raw");

var soundPlaying = false;
var options = new AudioInjectionOptions();
options.position = Vec3.sum(Camera.getPosition(), Quat.getFront(MyAvatar.orientation));
options.volume = 0.5;
options.loop = true;
var playing = false;
var ball = false;

function maybePlaySound(deltaTime) {

...

        //playing the sound
        soundPlaying = Audio.playSound(sound, options);
        print("Started sound looping.");
        Script.update.disconnect(maybePlaySound);
    }
}

...

```

## void stopInjector(AudioInjector injector)
Description: `stopInjector` stops the playback of a given AudioInjector. 

## Example:

Take a look at this snippet of `playSoundLoop.js`:

```

function maybePlaySound(deltaTime) {

...
        //starting the sound
        soundPlaying = Audio.playSound(sound, options);
        print("Started sound looping.");
        Script.update.disconnect(maybePlaySound);
    }
}
        
function scriptEnding() {
    if (Audio.isInjectorPlaying(soundPlaying)) {

        //stopping the sound
        Audio.stopInjector(soundPlaying);
        Entities.deleteEntity(ball);
        print("Stopped sound.");
    }

...

```

