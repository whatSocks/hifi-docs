---
layout: doc
title: AudioInjectionOptions
collection: api
category: Audio
---

## orientation
type: object
Description: A quaternion describing in which direction the AudioInjector is facing. 
Default Value: {x:0,y:0,z:0,w:1}

## position
type: object
Description: The source of the `Sound` from the `AudioInjector`. When creating and testing sounds, set this value close to `MyAvatar.position`.
Default Value: {x:0,y:0,z:0}

## isStereo
type: boolean
Description: `isStereo` describes whether or not the `Sound` should be played in stereo or not. 

## volume
type: float
Description: `volume` is a float between 0 and 1 that describes how loud is the audio at the source point.
Default Value: 1

