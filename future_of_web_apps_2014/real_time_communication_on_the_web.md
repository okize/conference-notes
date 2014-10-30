## Real-time communication on the web, for everyone!

### Lisa Larson-Kelley

__Summary:__
WebRTC is a powerful open-source project that seamlessly enables real-time communication (RTC)– baked right into modern web browsers. This means web developers can now incorporate video, voice and data sharing using peer-to-peer connectivity via simple JavaScript APIs, with no plugins or additional installs required. In this session, Lisa Larson-Kelley introduces the fundamentals of WebRTC, explaining its elements and capabilities in easy-to-understand terms, and walks through a simple ‘hello world’ application using the WebRTC API and open source libraries. With over 10 years of experience with real-time communication apps, Lisa shares her perspective and enthusiasm for RTC – you'll leave wanting to create your own innovative apps with this rapidly evolving technology that is poised revolutionize how we communicate on the web.

---

[slides](http://learnfromlisa.com/talks/fowa2014/WebRTC_FOWA_2014_final_16-9.pdf)

[Is WebRTC ready yet?](http://iswebrtcreadyyet.com/)

webRTC is a javascript API

http://auduno.github.io/clmtrackr/examples/facesubstitution.html

* MediaStream - web cam, microphone
* RTCDataChannel - allows peers to share generic data
* RTCPeerConnection - enables connection between clients, bandwidth management & encryption built in

flow:
* initialize and introduce
* exchange client info
* NAT traversal
* communicate!

STUN, TURN & ICE

STUN - session traversal utilities (around) NAT; tells you what your external IP address is; AKA hole punching

TURN - traversal using relays (around) NAT; acts as relay server, never steps out of the way

ICE - interactivity connectivity establishment; tries STUN & TURN until connection works

#### how to get started

[Learn WebRTC](http://learnfromlisa.com/learn-webrtc/)

* core programming skills
* editor
* webcam and microphone
* latest build of Chrome/Firefox

#### Some ready-to-use services

* Instant free video conferencing
  * apprtc.appspot.com AddLive.com
  * Vline.com
  * Vsee.com (free and premium) (and more every day!)

* WebRTC services and platforms
  * Tokbox.com Open Tok platform Appear.in
  * Vidyo.com
  * rtc.io
  * Xirsys.com hosted server infrastructure

* Prebuilt frameworks – Telephony
  * Phono - Open source JavaScript phone API
  * sipML5 - Open source JavaScript SIP client
  * FreeSWITCH - Scalable open source cross-platform service

* Prebuilt frameworks – Web
  * PeerJS
  * SimpleWebRTC
  * easyRTC
  * webRTC.io
  * RTC.io (node toolbox)
  
