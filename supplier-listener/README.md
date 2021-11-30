---
description: >-
  Listens for an event in the Supplier's dApp and sends a command to the
  Supplier's IoT platform.
cover: ../.gitbook/assets/skey_network_logoPodstawowe_RGB_01_whiteBG.png
coverY: 0
---

# Supplier Listener

It consists of three elements:

* Blockchain Worker - Parses blockchain transactions, supplies data for Iot Worker or Unique Worker.
* IoT Worker - Builds requests to IoT server, uses data from queue supplied by Blockchain Worker or Unique Worker (filters unique data from many Blockchain Workers).
* Unique Worker - Filters unique actions by transaction id between Blockchain Workers and Iot Workers.
