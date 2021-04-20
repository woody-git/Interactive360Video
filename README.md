**Interactive 360° Video using AWS**

This reposistory provide a simple web player that creates a WebXR scene, using Babylon.js framework, and inclduding a 360° video streamed in the scene, in order to create a live 360° video with interactive componenet provided by webXR.

You can use this player with AWS Elemental Media Services or with Amazon Interactive Video Service.

Reference Architecture

**Setup AWS Elemental MediaLive**

In order to setup the solution leveraging on AWS Elemental MediaLive, the first step is to use the Live Streaming solution, that provide a Cloudformation tamplate for live streaming. This solution setups MediaLive, MediaStorage and Cloudfront in order to encode and distribute an live streaming solution.
You can find the solution here: https://aws.amazon.com/it/solutions/implementations/live-streaming-on-aws/

In order to use the player in this repository, you have to setup the Live Streaming solution in the MediaStorage option and with RTMP PUSH.

In the default player 2 livestreams are managed and there is a reference to a 4K streaming. In order to obtain that you have to add a 4K output to MediaLive.
You can reference the 4K manifest, directly in the "stream_secondary" variable of the player, in order to swith from adaptive bitrate to a forced stream to 4K.

**Setup IVS**

For Interactive Video Service solutoin you just need to create a streaming channel on IVS and then reference the generated endpoint in the "stream_main" variable in the player


