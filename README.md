# [starlink.otternet.ca](http://starlink.otternet.ca)

Information about my starlink experience, with statistics and monitoring information etc.

Some headers are clickable links to separate pages.

---
Overview
* [Location](#Location)
* [Background](#Background)
* [Dishy Placement](#Dishy-Placement)
* [Observations](#Observations)
* [Firmware](#Firmware)
* [Network](#Network)

---
## Location
Eastern Townships, Quebec, Canada.

Latitude: 45.64

## Background

My home does not have any other option than 5/1 Mbps ADSL connection from [Bell](http://www.bell.ca) phone lines. The subscription is through [Virgin](https://www.virginmobile.ca/en/home/index.html), $30 per line per month. 2 Lines with a [TL-R470T+ load balancer](https://www.tp-link.com/us/business-networking/load-balance-router/tl-r470t+/). There is a nearby Bell tower that can deliver 200+ Mbps but neither my wallet nor my company phone manager would accept that as primary network access.

The ADSL lines work pretty well to load balance and [fast.com](http://fast.com) can sometimes max it at 11-12 MBps which means that [Virgin](https://www.virginmobile.ca/en/home/index.html) usually deliver the posted speed for the plan and sometimes even more. The bad thing is that you need to call them every time the line goes bad and they will reconfigure the connection.

One ADSL line will be kept as failover until Starlink is proven reliable for full work days.

### Starlink Timeline
```
- Preorder: February 11 2021
- Full order: July 8 2021
- Delivered: July 13 2021
```
### Virgin Decomission Timeline
```
2021-07-20: 
Called to check which of the ADSL lines is more reliable and faster. Plans paid for until Aug 6.
```

## [Dishy Placement](./placement/)

There are some trees that is blocking to the west/north. The starlink status page shows mixed amounts of red all the way between W and N. The other directions are clear.

### Initial test setup

2021-07-13

Placed the Dishy with the tripod in the garden, some tomato plant obstructions. 

Initial speed test: 120 MBps

### Temporary setup

2021-07-15

The dishy is mounted with the tripod on top of a metal pole that is in turn mounted in an [Oasis tripod](http://www.satelliteoasis.com/2-in-od-satellite-dish-tripod-for-directv-slimline-hd-dish/). Placed in the garden corner next to the tomato plants.

Started to collect [metrics](./network/statistics) from the Dishy API

#### Connectivity status:
- 2021-07-18T00:00 Last 12 Hours
    * Obstructed: 7 seconds
    * Other Outages: 1 minute

- 2021-07-18T00:00 Last 12 Hours
    * Obstructed: 3 seconds
    * Other Outages: 9 seconds



### Long term setup.

2020-07-19

Same place, new mounting. Metal pole with the [Starlink pipe adapter](https://shop.starlink.com/products/ca-consumer-mount-pipeadapter-grey) in the [Oasis tripod](http://www.satelliteoasis.com/2-in-od-satellite-dish-tripod-for-directv-slimline-hd-dish/).

#### Connectivity status:
- 2021-07-20T17:00:00 Last 12 Hours
    * Obstructed: 2 minutes
    * Other Outages: 3 minutes

- 2021-07-28T23:00:00 Last 12 Hours
    * Obstructed: 28 seconds
    * Other Outages: 40 seconds

## Observations
It seems the dish reset some "knowledge" after reboot. Obstructions went up after restart even though a slightly higher altitude of the Dishy. The obstructions image from the Dishy statistics shows a bit less red obstructions than before.

## Firmware

* __e825ab2c-1e21-4e24-bc77-6ffe80e76669.uterm.release__ 2021-07-28 02:57:59
    - Interruptions dropped significantly
* __6390f89c-448c-4fe6-8e1c-14708993ef7c.uterm.release__ 2021-07-26 18:41:54
* __2bc83694-2dec-48c8-9061-88b86cdd5d89.uterm.release__ 2021-07-21 22:38:26
    - Interruptions increased
* __4990ce8d-5028-4e51-a015-e9ab1b1ebe1a.uterm.release__
2021-07-15 22:01:31
    - Initial firmware version

## [Network](./network)
- Virgin ADSL 5/1 Mbps
- Starlink Internet
- Starlink Router
- ASUS Router

## [Monitoring & Statistics](./network/statistics)
My [Starlink monitoring & statistics](./network/statistics) setup

My [Starlink Dashboard](https://grafana.otternet.ca/d/ymkHwLaMz/) (Live data)
