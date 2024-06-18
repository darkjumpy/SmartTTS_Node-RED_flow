# SmartTTS Node-RED flow

![image](https://github.com/darkjumpy/SmartTTS_Node-RED_flow/assets/58175895/793e5b85-22d9-498d-b784-fd0ec5cee70b)


How it works:

If nothing is playing, TTS will say the message and set the previous volume.

If the speaker is playing something from URL, Spotify or YouTube music, TTS will 
say message, set the previous volume, and resume playing.

Known issues: <br/>
- If you are playing a playlist directly from YouTube music instead of ytube music player integration,
then after TTS playlist is searched by name. Because of that resumed playlist may be different than played before.
Also, Smart TTS has to skip music in the album until it finds the right one. That may take some time.

- If you are sending TTS for a group, and speakers of this group aren't in this same state, 
then it causes unwanted behavior

If you know how to fix any of those issues please open an issue with a solution.

Requirements:
- Home Assistant <br/>
If you are using Google Home speakers <br/>
- Official Home Assistant Google Cast integration <br/>
If you are using Alexa speakers <br/>
- Custom Home Assistant Alexa Media Player integration (https://github.com/custom-components/alexa_media_player) <br/>
If you are using Spotify: <br/>
- Official Home Assistant Spotify integration
- Custom Home Assistant Spotcast integration (https://github.com/fondberg/spotcast) <br/>
If you are using YouTube music: <br/>
- Custom Home Assistant ytube music player integration (https://github.com/KoljaWindeler/ytube_music_player)

How to start:
1. Double click on Smart TTS node under subflows
2. Setup your config
3. Done!

Input variables:

- msg.speaker (required)
    ID of Google Cast-enabled speaker.

- msg.message (required)
    TTS message.

- msg.volume (optional)
    The volume of TTS messages. If the variable is not 
    provided volume is not changing.
    
- msg.tts_service (optional)
    TTS service used to say message. If variable 
    is not provided default TTS service is used.
    
- msg.tts_language (optional)
    Language of Google TTS message.

Other info:

This project was maintained under [this page](https://flows.nodered.org/flow/d0f137bc6323fd8200b8221cea22d713), but I no longer have access to this Node-RED project.<br/>
This is currently the official repository of the project.
