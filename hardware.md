# Home Lab 2023
## Hardware
### Compute
| Machine | OS | CPU | RAM | Disk | GPU | Other | Purpose |
| ------- | -- | --- | --- | ---- | ---- | -------| ------- |
| Lenovo m92p | Debian | i7-3770 | 16GB | 1T SSD | &cross; | &cross; | Dev, k8s, mgmt |
| Whitebox | Debian (Proxmox)| Ryzen 7 3700x | 64GB |  1T OS, 7x 2TB Hitachi |  GTX 1080 | 10Gbe SFP, LSI-??? Raid | Zoneminder, k8s |
| IBM x3850 x5 | Debian (Proxmox) | 4x Xeon E7-4820 | 512GB | 8x 240GB Kingston SSDs | &cross; | ServeRAID M1015, 10Gbe SFP | Electric Bill Scaler |
- Build a few Lenovo ThinkCentres and part out IBM box ?
- Dump proxmox altogether for k8s, pros, cons ?
    - GPU pass-through, one flavor of k8s simpler than another or doesn't matter ?
- NVR; zoneminder is not my jam some alternatives to look into;
    - Shinobi (tensorflow out of box)
    - Xeoma
    - Frigate (opencv/tensorflow out of the box)
    - Viseron (commands via MQTT, hardware accel. out of box)

### Networking
| Make/model | Ports | PoE | Purpose | To Decom? |
| ---------- | ------| --- | ------- | --------- |
| Ubi - Edge ER-X | 6 | &check; | Route all the things | &check; |
| NetGear ProSafe | 24 | &check; | Primary | &check; |
| NetGear GS308 | 8 | &cross; | | |
| TP-Link TL-SF1006P | 6 | &check; | PoE for garage | ? |
- Replace Edge ER-X with UDM/UDM Pro?
    - UDM vs UDM Pro IPS/IDS throughput ?
    - UDM IPS/IDS throughput ~ 850Mbps (per spec sheet)
    - UDM is NOT rack mountable, R2-D2 trash can design (4.33 x 7.25" footprint), and no SFP+
- Replace ProSafe w/ 24 port unifi device?
    -  24 Port PoE non-pro
        - 25W max consumption
        - 26 Gbps non-blocking throughput
        - 52 Gbps switching cap.
        - -5-40C op. temp
        - 2x 1Gbps SFP
        - 120W power supply
        - no 60w poe
        - weight w/ rack ears 6.81lb
    - 24 Port PoE pro
        - 50W max (excl. poe)
        - 44 Gbps non-blocking throughput
        - 88 Gbps switching cap.
        - -5-40C op. temp
        - 2x 1/10Gbps SFP+
        - 450w power supply
        - P17-24 PoE++
        - weight w/ rack ears 9.68lb
- Cat 6 Runs
    -   [x] Living room
    -   [ ] Front Hallway
    -   [ ] Upstairs Hallway
    -   [ ] Master BR
    -   [ ] Guest 1
    -   [ ] Guest 2
    -   [ ] Guest 3
    -   [ ] Kitchen
    -   [ ] Garage Conduit (needs media converters)
