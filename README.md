# Awesome WebHID [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

> Curated list of resources relating to the WebHID (Human Interface Device) API

WebHID is a browser API (`navigator.hid`) that provides access to HID input/output devices. It's a higher level of abstraction than the WebUSB and Web Bluetooth APIs, but lower than the Gamepad API and basic input (pointer/keyboard).

Contributions welcome. Add links through pull requests or create an issue to start a discussion. See [contribution guidelines](contributing.md).


## Contents
- [Status](#status)
- [Good to know](#good-to-know)
- [Specification & documentation](#specification--documentation)
- [Blogs & articles](#blogs--articles)
- [Talks & videos](#talks--videos)
- [Devices](#devices)
- [Tools](#tools)
- [Bluetooth, USB, & HID reference](#bluetooth-usb--hid-reference)
- [Libraries](#libraries)
- [Demos, experiments & hacks](#demos-experiments--hacks)
- [Real-world applications](#real-world-applications)
- [Inspiration from elsewhere](#inspiration-from-elsewhere)
- [Ideas](#ideas)
- [Forums & discussion](#forums--discussion)
- [Miscellaneous](#miscellaneous)
- [Related](#related)


## Status
Enabled by default since Chrome 89 (March 2021).

## Good to know
* WebHID is not a W3C Standard nor is it on the W3C Standards Track<sup>[(ref)](https://wicg.github.io/webhid)</sup>.
* Devices that generate trusted input (e.g. keyboards, mice, security keys) will not be accessible. Such devices define their reports in [top-level HID collections](https://docs.microsoft.com/en-us/windows-hardware/drivers/hid/top-level-collections) that will be considered protected usages<sup>[(ref1)](https://groups.google.com/a/chromium.org/d/msg/blink-dev/OaDCpCaEe_4/uZ0z7frlAAAJ]), [(ref2)](https://discourse.wicg.io/t/human-interface-device-hid-api/3070/6])</sup>.
* Access to a device must be granted by the user via a chooser dialog provided by the browser, similarly to WebUSB and Web Bluetooth. Launching the chooser must be done from the context of a user gesture (e.g. a mouse click).
* Neither the WebUSB<sup>[(ref)](https://github.com/WICG/webusb/issues/29)</sup> or Web Bluetooth<sup>[(ref)](https://github.com/WebBluetoothCG/web-bluetooth/issues/393)</sup> APIs allow access to HID-class devices.


## Specification & documentation
* [WebHID API Specification](https://wicg.github.io/webhid) (Web Platform Incubator Community Group (WICG)) - Including introduction, motivating applications, and security/privacy.
* [WebHID Explainer](https://github.com/WICG/webhid/blob/master/EXPLAINER.md) - The what & why in a nutshell, including basic terminology and an example. Some API details outdated.
* [WebHID (Human Interface Device) - Chrome Platform Status](https://www.chromestatus.com/feature/5172464636133376)
* [Chromium implementation tracking bug: WebHID API](https://bugs.chromium.org/p/chromium/issues/detail?id=890096) - Labelled with targeted & stable release versions; see the [development/release calendar](https://www.chromium.org/developers/calendar).


## Blogs & articles
* [Upcoming WebHID API - access Bluetooth/USB HID devices in web applications](https://blog.scottlogic.com/2019/04/03/upcoming-webhid-api.html) - An introduction to WebHID with an example showing how to open, listen for input and send output to a device. 


## Talks & videos
None yet.


## Devices
*Devices that work well with WebHID, and device-specific abstraction libraries. Do also file an issue to inform others of devices that don't. Not all devices in the USB HID device class will communicate using the high-level abstractions.*

* [Blink(1)](https://blink1.thingm.com) - notification light (see demos section, and prior art [node-blink1](https://github.com/sandeepmistry/node-blink1)).
* [BlinkStick](https://www.blinkstick.com) - light devices and controllers (see demos section, and prior art [blinkstick](https://github.com/arvydas/blinkstick-node))
* [Elgato Stream Deck](https://www.elgato.com/en/gaming/stream-deck) - programmable button panel (see demos, and libraries)
* [Razer Kraken Kitty Edition Headset](https://www.razer.com/gaming-headsets/razer-kraken-kitty) - headset with customizable LED lighting
* [Sony DualShock 4](https://www.playstation.com/en-us/explore/accessories/gaming-controllers/dualshock-4/) - controller for PlayStation 4 (see libraries section)
* [Nintendo Joy-Cons](https://www.nintendo.com/store/hardware/joy-con-and-controllers/) (see demos, and libraries)

### Candidates
* [Cleware](http://www.cleware-shop.de/en_US) - sensors, switches, and lights (see [clewarecontrol](https://www.vanheusden.com/clewarecontrol/), [sniner/cleware](https://github.com/sniner/cleware))
* [Espruino Pico](https://www.espruino.com/Pico) board - has an [USB HID mode](https://www.espruino.com/USB), might also be useful as an emulator?
* Jabra headsets (see [Standard USB HID Specification](https://developer.jabra.com/site/global/sdks/web/index.gsp))
* Nintendo Switch Pro Controller<sup>[(ref)](https://chromium.googlesource.com/chromium/src.git/+/05ac99d21920fec606ac1e360a2534921938cc85)</sup>
* Sony DualShock 3<sup>[(ref)](https://chromium.googlesource.com/chromium/src.git/+/05ac99d21920fec606ac1e360a2534921938cc85)</sup>
* [X-keys](https://xkeys.com/xkeys.html) - keyboards, switches, analog controls, and pedals (see [HID Data Reports](https://xkeys.com/software/developer/developerhiddatareports.html), [Integration](https://xkeys.com/software/developer/developerintegration.html), [xkeys](https://github.com/SuperFlyTV/xkeys), [node-xkeys](https://github.com/macoss/node-xkeys))
* Xbox Wireless Controller<sup>[(ref)](https://chromium.googlesource.com/chromium/src.git/+/05ac99d21920fec606ac1e360a2534921938cc85)</sup>


## Tools
*Software that aids working with devices.*

* [USBDeview](https://www.nirsoft.net/utils/usb_devices_view.html) - View device information.
* [USB Device Tree Viewer](https://www.uwe-sieber.de/usbtreeview_e.html) - View device information including interface and HID descriptors.
* [node-hid](https://github.com/node-hid/node-hid) - Cross-platform library for accessing USB HID devices from Node.js or Electron.


## Bluetooth, USB, & HID reference
*Information about the underlying technologies, including specifications and explanations.*

* [Human Interface Devices (HID) Information](https://www.usb.org/hid) (USB Implementers Forum (USB-IF)) - Including the device class definition, and usage tables.
* [Human Interface Device Profile specification](https://www.bluetooth.com/specifications/profiles-overview) (Bluetooth Special Interest Group (SIG)) - "An adaptation of the USB HID Specification to operate over a Bluetooth wireless link."
* [A Closer Look at HID Class](https://www.tracesystemsinc.com/USB_Tutorials_web/USB/B1_USB_Classes/Books/A3_A_Closer_Look_at_HID_Class/slide01.htm) - Explanation of USB HID, with enough detail yet easy to follow.
* [Understanding HID report descriptors](https://who-t.blogspot.com/2018/12/understanding-hid-report-descriptors.html) - Understanding devices' descriptions of themselves.


## Libraries
* [TheBITLINK/WebHID-DS4](https://thebitlink.github.io/WebHID-DS4/) - using a DualShock 4 controller.
* [@elgato-stream-deck/webhid](https://github.com/julusian/node-elgato-stream-deck) - using the Elgato Stream Deck (see demos).
* [tomayac/joy-con-webhid](https://github.com/tomayac/joy-con-webhid) - using Nintendo Joy-Cons.


## Demos, experiments & hacks
* [WebHID Explorer](https://paulirish.github.io/webhid-explorer/) - Lil' demo web tool for conveniently viewing device info, monitoring input reports, and sending output/feature reports.
* [todbot/blink1-webhid](https://todbot.github.io/blink1-webhid/) - using the blink(1).
* [Elgato StreamDeck](https://julusian.github.io/node-elgato-stream-deck/) - using the Elgato Stream Deck (via [@elgato-stream-deck/webhid](https://github.com/julusian/node-elgato-stream-deck)).
* [robatwilliams/webhid-demos](https://github.com/robatwilliams/webhid-demos) - using the BlinkStick Strip.
* [tomayac/chrome-dino-webhid](https://github.com/tomayac/chrome-dino-webhid) - using Nintendo Joy-Cons.
* [tomayac/joy-con-webhid/demo/](https://tomayac.github.io/joy-con-webhid/demo/) - using Nintendo Joy-Cons.


## Real-world applications
* [Ergometer Space](https://ergometer-space.org) - Track your indoor rowing exercise, alone or with other online users.
* [Kraken Kitty Edition Controller](https://sarahemm.github.io/razerkitty-webhid/) - Control the LED lighting on your Razer Kraken Kitty Edition headset.
* [Remap](https://remap-keys.app) - Customize a keyboard's keymap (see [remap-keys/remap](https://github.com/remap-keys/remap)).


## Inspiration from elsewhere
*Transferrable inspiration from related areas such as general Bluetooth/USB HID, Web Bluetooth, and WebUSB.*

* [chrome.hid API sample](https://github.com/GoogleChrome/chrome-app-samples/tree/master/samples/hid) - Generic input/output Chrome App sample.
* [blink(1) using the chrome.hid API](https://github.com/GoogleChrome/chrome-app-samples/tree/master/samples/blink1) - Chrome App sample that controls a [Blink(1)](https://blink1.thingm.com) notification LED.
* [Interacting with USB HID devices from web apps](https://keetrax.com/blog/2015/01/interacting-usb-hid-devices-web-apps/) - Using a Chrome App as a go-between between a dictation foot pedal and a web application (2015).
* [Web Bluetooth Demos](https://github.com/WebBluetoothCG/demos) (Web Bluetooth Community Group) - Various, plus links to others.
* [Griffin Powermate Playground](https://github.com/beaufortfrancois/sandbox/blob/gh-pages/webusb/griffin-powermate.html) - Using WebUSB.
* [node-hid examples](https://github.com/node-hid/node-hid#examples) - Despite the name, most directly use low-level read/write operations rather than HID abstractions.


## Forums & discussion
* [Human Interface Device (HID) API](https://discourse.wicg.io/t/human-interface-device-hid-api/3070) (WICG Discourse) - Introduction by the editor of the specification, and answers to questions.
* [Intent to Implement: WebHID (Human Interface Device)](https://groups.google.com/a/chromium.org/forum/#!msg/blink-dev/OaDCpCaEe_4/3taK3m75DAAJ) (chromium.org blink-dev) - Introduction by the editor of the specification, and answers to questions.


## Miscellaneous
None yet.


## Related
* [Web Bluetooth API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Bluetooth_API) (MDN)
* [WebUSB API](https://developer.mozilla.org/en-US/docs/Web/API/USB) (MDN)
* [chrome.hid API](https://developers.chrome.com/apps/hid) - For Chrome Apps.
* Web Serial API
  * [Specification](https://wicg.github.io/serial) (WICG)
  * [Discussion](https://discourse.wicg.io/t/serial-api-moving-from-web-of-sensors-cg-to-web-incubator-cg/2940) (WICG Discourse)
  * [Chromium implementation tracking bug: Web Serial API](https://bugs.chromium.org/p/chromium/issues/detail?id=884928)


## License
[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
