# CARLA_2_CSEAMAN
CAN bus traffic generated from CARLA simulation retransmitted by Raspberry Pi CAN Gateway. The dataset includes CAN bus raw frames with Spoofing/Random injection/Random modification and Replay attacks, in .log format. 

## Simulation and data-generation setup

- **Simulator:** CARLA 0.9.16
- **Map:** `Town10HD_Opt`
- **Simulation mode:** Asynchronous, with a variable time step
- **Physics substepping:** Enabled; maximum substep delta time of 0.01 s
  and maximum of 10 substeps
- **Vehicle:** `vehicle.mercedes.coupe_2020`
- **Vehicle physics:** CARLA default parameters
- **CAN gateway:** Raspberry Pi using SocketCAN
- **CAN bitrate:** 500 kbit/s
- 
## Folder structure

```text
CARLA_2_CSEAMAN/
├── README.md
├── dataset/
    ├── no_attack/
    ├── random_injection/
    ├── random_modification/
    ├── replay/
    └──  spoofing/

```
## File structure
The CAN datasets are stored as .log file. Each row inside the file consists of the following information:

| Timestamp | Channel (`c`) | CAN ID (`id`) | Length (`l`) | Payload | 
|:-------------|--------------:|----------------:|:--------------|-------------:|:--------|
| 000.000000 | can0 | 128 | [8] | `00 34 00 00 00 00 00 00` | 00 |
| 000.000248 | can0 | 168 | [8] | `00 00 00 01 00 00 00 00` | 00 |
| 000.000498 | can0 | 1A9 | [8] | `00 00 00 00 00 00 00 00` | 00 |

