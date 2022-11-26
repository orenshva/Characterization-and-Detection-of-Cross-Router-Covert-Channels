# Characterization and Detection of Cross-Router Covert Channels

This repository contains the source code and data used in the paper "Characterization and Detection of Cross-Router Covert Channels". The full data used in the paper is accessible with [this link](https://drive.google.com/drive/folders/1h1lWvswOnmDA2hYyrrAQ5CUjDiv0dTMG?usp=sharing).

The paper presentes two network timing covert channel that break logical isolation between two networks hosted by a single shared router: CRCC and Wi-Fi Micro-jamming attacks. 

By using these covert channels, we were able to leak information between the two networks, even though the overt communication is blocked. By deliberately exhausting the router's resources according to the leaked information bits, a machine in the host network can signal the information to a machine in the guest network.

![Picture3](https://user-images.githubusercontent.com/61083859/204087248-ce8bcdbe-72d2-4e32-afa9-cf885fa11bb3.png)

Also, the paper presents a method of detecting both attacks using a ML/DL detector. The models extract behavioral features from the network traffic and can detect anomalies caused by these attacks. The models used are semi-supervised models that perform novelty detection.

To detect the attacks we used:

* CRCC detection: Deep Autoencoder.
* Wi-Fi Micro-jamming detection: Local Outlier Factor (LOF).

## Getting Started

### Repository contents

The Attacks folder contains the source code for both attacks along with documents and pictures to help assembling their setup.

The Defense folder contains the source code of the ML/DL detector, the feature extractor, and the actual features used in the paper.

### Dependencies

* Python 3
* Scapy
* tcpdump
* Wireshark + tshark

### Setup

* The setup should be built as described in the paper.
* You can also refer to the manuals in the "Attacks" folder.

## Authors

Main author: Oren Shvartzman (orenshva@post.bgu.ac.il)

co-authors: Adar Ovadya, Kfir Zvi, Omer Schwartz, Rom Ogen, Yakov Mallah, Niv Gilboa, and Yossi Oren

## Acknowledgments

This work was supported by Israel Science Foundation
grants 702/16 and 703/16. We thank Eyal Ronen for
providing the inspiration and equipment for initiating our
Wi-Fi micro-jamming research. We also thank Clémentine
Maurice for providing the motivation for our cross-router
covert channel research, and our WOOT shepherd, Paul
Pearce, for helping us improve the paper. Finally, we would
like to thank Yagel Netanel for designing and implementing
large parts of the CRCC attack system which was used to
collect data for this research.
