# Ullo Labs

## Introduction

This landing page lists the public repositories published by Ullo alongside our products ([http://ullo-world.fr/](http://ullo-world.fr/)) and our research lab ([https://labs.ullo.fr/](https://labs.ullo.fr/)).

For code-related enquiries, you can get in touch with us using the issue tracker of the corresponding repository, or you can send an e-mail to `support at ullo dot fr`.

## Products

Instructions and repositories sorted by product.

### Echo

On Echo, each sensor and metric have their own LSL stream sending information in real time. For those not already familiar with LSL (LabStreamingLayer), it is a communication protocol that is almost becoming a standard with physiological recordings, more details on their official repository [https://github.com/sccn/labstreaminglayer](https://github.com/sccn/labstreaminglayer). A LSL stream has two main information: the name and the type. We use the "type" to describe... the type of signal we are sending (brain activity, heart rate, breathing, etc.) and the "name" to differentiate between the Echo. For example when using the breathing belt with an Echo named "pink", then you can get the breathing rate through the stream of name "eachopink" and type "breamthingrate". Note that you would need to be connected on the same wifi as the Echo in order to see this LSL stream. LSL is a very flexible and practical protocol, even though it goes through the network you don't need to know any IP adres to use it, and one can easily browse all available streams.

The best option to record data from LSL would be to use LabRecorder, aimed at recording experiments, that can ensure strong time synchronization between various streams. You can find the software here: [https://github.com/labstreaminglayer/App-LabRecorder](https://github.com/labstreaminglayer/App-LabRecorder), but unfortunately the last version suffers from a bug that can prevent it from finding all streams coming from an Echo, because here multiple streams share the same name ([see here the discussion about the regression](https://github.com/labstreaminglayer/App-LabRecorder/issues/31)). Hence you would have to use an order version (prior to 1.13), a binary for windows is available on [SCCN's FTP server](ftp://sccn.ucsd.edu/pub/software/LSL/Apps/LabRecorder-1.12d.zip). LabRecorder records in XDF format, not yet widely implemented, unfortunately, even though there are code to is it in Matlab and python, see e.g. [https://github.com/sccn/xdf/](https://github.com/sccn/xdf/) and [https://github.com/xdf-modules](https://github.com/xdf-modules).

To facilitate recordings of signals from Echo, we created a python script that can export it in a more traditional CSV format, it is available here: [https://github.com/UlloLabs/LSL2Logs](https://github.com/UlloLabs/LSL2Logs). This latter code should be straightforward to use, but it is still new, so don't hesitate to report any issues you might have with it.

## Repositories

- [LSL2Logs](https://github.com/UlloLabs/LSL2Logs): get data from LSL streams and write to (verbose) CSV files.
- [liblsl](https://github.com/UlloLabs/liblsl/tree/dev-leak): we published a fork of the LSL library that can drastically decrease CPU utilization, especially on machine with limited ressources and streams with low sampling rate (below 100hz). See discussions on [https://github.com/sccn/liblsl/pull/70](https://github.com/sccn/liblsl/pull/70) and [https://github.com/sccn/liblsl/pull/71](https://github.com/sccn/liblsl/pull/71).

## Related work

Historically we have been contributed to other places, e.g. [https://github.com/conphyture](https://github.com/conphyture).

See also code snippets hosted on: [https://gitlab.com/ullo/bricbroc/snippets](https://gitlab.com/ullo/bricbroc/snippets).
