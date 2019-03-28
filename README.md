# Awesome WebHID [![Awesome](https://awesome.re/badge-flat.svg)](https://awesome.re)

> Curated list of resources relating to the WebHID (Human Interface Device) API


## Contents
- [Specification & documentation](#specification--documentation)
- [Blogs & articles](#blogs--articles)
- [Talks & videos](#talks--videos)
- [Devices](#devices)
- [Tools](#tools)
- [Bluetooth, USB, & HID reference](#bluetooth-usb--hid-reference)
- [Demos, experiments & hacks](#demos-experiments--hacks)
- [Real-world applications](#real-world-applications)
- [Inspiration from elsewhere](#inspiration-from-elsewhere)
- [Ideas](#ideas)
- [Forums & discussion](#forums--discussion)
- [Miscellaneous](#miscellaneous)
- [Related](#related)


## Specification & documentation
* [WebHID API Specification](https://wicg.github.io/webhid) (Web Platform Incubator Community Group (WICG))
* [WebHID Explainer](https://github.com/WICG/webhid/blob/master/EXPLAINER.md)
* [WebHID (Human Interface Device) - Chrome Platform Status](https://www.chromestatus.com/feature/5172464636133376)


## Blogs & articles
None yet.


## Talks & videos
None yet.


## Devices
*Devices that work well with WebHID. Do also file an issue to inform others of devices that don't. Not all devices in the USB HID device class will communicate using the high-level abstractions.*


### Candidates
* [Blink(1)](https://blink1.thingm.com) - notification light (see [node-blink1](https://github.com/sandeepmistry/node-blink1))
* [BlinkStick](https://www.blinkstick.com) - light devices and controllers (see [blinkstick-node](https://github.com/arvydas/blinkstick-node))
* [Cleware](http://www.cleware-shop.de/en_US) - sensors, switches, and lights (see [clewarecontrol](https://www.vanheusden.com/clewarecontrol/), [sniner/cleware](https://github.com/sniner/cleware))
* [X-keys](https://xkeys.com/xkeys.html) - keyboards, switches, analog controls, and pedals (see [HID Data Reports](https://xkeys.com/software/developer/developerhiddatareports.html), [Integration](https://xkeys.com/software/developer/developerintegration.html))


## Tools
*Software that aids working with devices.*

* [USBDeview](https://www.nirsoft.net/utils/usb_devices_view.html) - view device information
* [USB Device Tree Viewer](https://www.uwe-sieber.de/usbtreeview_e.html) - view device information including interface and HID descriptors
* [node-hid](https://github.com/node-hid/node-hid) - cross-platform library for accessing USB HID devices from Node.js or Electron


## Bluetooth, USB, & HID reference
*Information about the underlying technologies, including specifications and explanations.*

* [Human Interface Devices (HID) Information](https://www.usb.org/hid) (USB Implementers Forum (USB-IF)) - including the device class definition, and usage tables
* [Human Interface Device Profile specification](https://www.bluetooth.com/specifications/profiles-overview) (Bluetooth Special Interest Group (SIG)) - "an adaptation of the USB HID Specification to operate over a Bluetooth wireless link"
* [A Closer Look at HID Class](https://www.tracesystemsinc.com/USB_Tutorials_web/USB/B1_USB_Classes/Books/A3_A_Closer_Look_at_HID_Class/slide01.htm)
* [Understanding HID report descriptors](https://who-t.blogspot.com/2018/12/understanding-hid-report-descriptors.html)


## Demos, experiments & hacks
None yet.


## Real-world applications
None yet.


## Inspiration from elsewhere
*Transferrable inspiration from related areas such as general Bluetooth/USB HID, Web Bluetooth, and WebUSB.*

* [chrome.hid API sample](https://github.com/GoogleChrome/chrome-app-samples/tree/master/samples/hid) - a generic input/output Chrome App sample
* [blink(1) using the chrome.hid API](https://github.com/GoogleChrome/chrome-app-samples/tree/master/samples/blink1) - a Chrome App sample that controls a [Blink(1)](https://blink1.thingm.com) notification LED
* [Interacting with USB HID devices from web apps](https://keetrax.com/blog/2015/01/interacting-usb-hid-devices-web-apps/) - using a Chrome App as a go-between between a dictation foot pedal and a web application (2015)


## Ideas
*Great idea, no time or no device? File an issue to share.*

None yet.


## Forums & discussion
* [Human Interface Device (HID) API](https://discourse.wicg.io/t/human-interface-device-hid-api/3070) (WICG Discourse)
* [Intent to Implement: WebHID (Human Interface Device)](https://groups.google.com/a/chromium.org/forum/#!msg/blink-dev/OaDCpCaEe_4/3taK3m75DAAJ) (chromium.org blink-dev)


## Miscellaneous
None yet.


## Related
* [Web Bluetooth API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Bluetooth_API) - MDN
* [WebUSB API](https://developer.mozilla.org/en-US/docs/Web/API/USB) - MDN
* [chrome.hid API](https://developers.chrome.com/apps/hid) for Chrome Apps


## License
[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](https://creativecommons.org/publicdomain/zero/1.0/)
