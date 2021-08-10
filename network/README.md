# The Network

* [WAN](#WAN)
    * [ADSL](#ADSL)
    * [Starlink](#Starlink)
* [LAN](#LAN)
    * [ADSL LAN](#ADSL-LAN)
    * [Starlink LAN](#Starlink-LAN)
    * [Network Diagram](#Diagram)

## WAN

### ADSL

2 * Virgin Plus ADSL 5/1 Mbps. CAD $30/month each + tax

### Starlink

Dishy with Starlink router. CAD $148.32/month (tax included)

[My monitoring setup](./statistics/)

## LAN

### ADSL LAN

WiFi Router with 2 load balanced Virgin Plus ADSL lines.
- [D-Link DIR-878](https://ca.dlink.com/en/products/dir-878-ac1900-high-power-wi-fi-gigabit-router) router
- [TL-R470T+](https://www.tp-link.com/us/business-networking/load-balance-router/tl-r470t+/)  load balancer
- 2 * Virgin Steve Router

### Starlink LAN

WiFi routers hooked up to Starlink router as primary WAN. ADSL LAN connected as failover.
- 2 * [ASUS RT-AX58U](https://www.asus.com/ca-en/Networking-IoT-Servers/WiFi-Routers/ASUS-WiFi-Routers/RT-AX58U/) Routers (aimeshed)
- Starlink Router

### Diagram

```
                                    x                                   xxxxx   xxx xxx
                                     xxxx                             xxxx  xx xx xxx xx
                                         xxxx                         x        x   x   x
                                            xxxxx                    xxx Virgin/Bell  xxx
                                            xx  xxxxx               xx  xx    x     xx   x
                                            xxx     xxxx            x x  xx  xxxx    xxxxx
                                             xx        xx             │   xxxx  xxxxx
                                             xx                       │           │
      Starlink LAN                           xx                       │           │
                                             xx                       │           │
                                             xx                       │           │  ADSL LAN
                                             xx                       │           │
                                           xxxxx                      │           │
   ┌─────┐  ┌─────┐  ┌─────┐              xx xxxx                 ┌───┴───┐   ┌───┴───┐
   │  A  │  │  A  │  │  S  │             xx  xx xx                │   S   │   │   S   │
   │  X  │  │  X  │  │  L  │             x   xx   xx              │   T   │   │   T   │
───┤     │  │     │  │     │            xx   xx    xx             │   E   │   │   E   │
   │  5  │  │  5  │  │  R  │           xx    xx     xx            │   V   │   │   V   │
───┤  8  ├──┤  8  ├──┤  O  ├───────────────────      x            │   E   │   │   E   │
   │  U  │  │  U  │  │  U  │                                      │       │   │       │
───┤     │  │     │  │  T  │                                      │       │   │       │
   │     │  │     ├─ │  E  │ ──────────────────────────────────┐  └───┬───┘   └───┬───┘
───┤     │  │     │  │  R  │    Failover                       │      │           │
   └──┬──┘  └──┬──┘  └─────┘                                   │  ┌───┴───────────┴───┐
      │        │                                               │  │   LOAD BALANCER   │
   ───┴───  ───┴───                                            │  │                   │
                                                               │  └────────┬──────────┘
    ─────    ─────                                             │           │
                                                               │       ┌───┴───┐
     ───      ───                                              └───────┤   D   │
                                                                       │   I   │
                                                                      ─┤   R   │
                                                                       │       │
                                                                      ─┤   8   │
                                                                       │   7   │
                                                                      ─┤   8   │
                                                                       └───┬───┘
                                                                           │
                                                                        ───┴───

                                                                         ─────

                                                                          ───
```