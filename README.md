# Android-7.1.1-fails-to-play-.ts-audio

Steps to reproduce .ts audio playback failure bug:
1. install IntegrationTest.apk
2. copy and unzip testSingals.tar.gz to /sdcard/dolby/integrationtest/
3. launch "Integration Test" APP on Android 7.1.1
4. click Audio(OpenMAX-AL Buffer Player) -> 2 channel DD audio(TS)

Check the Logcat output, and we can see:  
......  
03-15 09:55:25.768 ?6172 ?6172 E BufferOpenMaxPlayer: Created instance of BufferOpenMaxPlayer  
03-15 09:55:25.840 ?2787 ?2968 E BufferQueueProducer: [com.dolby.ds/com.dolby.ds.playercontroller.TestPlayerActivity] connect: already connected (cur=1 req=1)  
03-15 09:55:25.856 ?6172 ?6172 E NativePlayerController: setDataSource() /mnt/sdcard/dolby/integrationtest/2ch_dd_audio.ts  
03-15 09:55:25.861 ?3014 ?3014 E MediaPlayerService: getDuration returned -2147483648  
03-15 09:55:25.863 ?3014 ?9040 E NuPlayer: no metadata for either audio or video source  
03-15 09:55:25.865 ?6172 ?9039 E libOpenSLES: Error after prepare: 1  
03-15 09:55:25.865 ?6172 ?9039 E BufferOpenMaxPlayer: Failed to open media content  
03-15 09:55:25.870 ?6172 ?9043 E JNICommonPlayer: JNICommonPlayer::postToJava  
03-15 09:55:25.870 ?6172 ?9043 E JNICommonPlayer: /JNICommonPlayer::postToJava  
03-15 09:55:25.926 ?6172 ?6172 E CommonOpenMaxPlayer: CommonOpenMaxPlayer::release  
03-15 09:55:25.926 ?6172 ?6172 E CommonOpenMaxPlayer: /CommonOpenMaxPlayer::release  
03-15 09:55:26.018 ?3006 ?3229 E AudioStream: getFramesAvailable: Unable to get available frames  
03-15 09:55:26.019 ?3006 ?3229 E AudioStream: getFramesAvailable: Unable to get available frames  
03-15 09:55:26.019 ?3006 ?3229 E AudioStream: getFramesAvailable: Unable to get available frames  
03-15 09:55:26.019 ?3006 ?3229 E AudioStream: getFramesAvailable: Unable to get available frames  
......  
