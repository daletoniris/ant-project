# Ant Project -- Formicario Digital

**Digital ant farm with Raspberry Pi, camera, and environmental sensors (2021)**

> From the kid who watched ants for hours in the backyard of la casa magica, to the engineer who built a digital system to observe them.

---

## What Is This?

A digital formicarium (ant farm) monitoring system built with **Raspberry Pi, PiCamera, and environmental sensors**. The system records time-lapse video of ant colonies while simultaneously measuring temperature, humidity, and light levels -- creating a complete dataset of colony behavior correlated with environmental conditions.

This project is a direct connection to Daniel's childhood: the same kid who built an ant farm in Villaguay to observe **emergent behavior and swarm intelligence** grew up to build a digital version with sensors and cameras.

## Features

- **Time-lapse Recording** -- Configurable video capture with PiCamera (resolution, duration, intervals)
- **Environmental Monitoring** -- DHT22 temperature/humidity + BH1750 light sensor via I2C
- **GUI Interface** -- PyQt5 desktop application with configuration panels
- **NDVI Analysis** -- Integration with Infrapix for vegetation index calculations
- **Automated Scheduling** -- Start time, video duration, and quantity configuration via TOML
- **MP4 Conversion** -- Automatic H.264 to MP4 conversion of recorded footage

## Hardware

- **Raspberry Pi** (2/3/4) -- Main computing platform
- **PiCamera** -- Video recording of the formicarium
- **DHT22** -- Temperature and humidity sensor (GPIO 20)
- **BH1750** -- Digital light level sensor (I2C bus)
- **IR LEDs** (optional) -- For night-time observation without disturbing the colony

## Configuration

The system is configured via `configs.toml`:

```toml
[tiempo]
fh_inicio = 2021-08-18T06:25:00
duracion_videos = 00:05:00
cantidad_videos = 10

[grabacion]
res_x = 640
res_y = 480
convert_mp4 = true

[preview]
on = true
fullscreen = false
```

## Key Files

| File | Description |
|------|-------------|
| `main.py` | Main tkinter-based application (early version) |
| `ant_project_updates/ant_project_sin_sensores/main.py` | Updated PyQt5 application with full sensor integration |
| `ant_project_updates/*/configs.py` | TOML configuration loader |
| `ant_project_updates/*/configs.toml` | Recording and sensor settings |
| `ant_project_updates/*/video.py` | PiCamera recording module |

## The Connection

```
Age 8:  Built an ant farm from glass and dirt.
        Watched ants for hours. No tools, no instruments.
        Just eyes and patience.

2021:   Built a digital ant farm with cameras and sensors.
        Same curiosity, better tools.
        Same question: how do simple agents create complex behavior?

2025:   Built TokioAI -- a WAF processing millions of requests.
        Same pattern: individual signals creating emergent intelligence.
        The ant farm never stopped.
```

The formicarium was always about **emergent behavior**: how do individual agents following simple rules produce complex collective intelligence? That question drives everything from this ant farm to the autonomous SOC systems Daniel builds today.

## Requirements

```
sudo apt-get install python3-pyqt5
sudo apt-get install python3-rpi.gpio
sudo apt install python3-smbus
pip3 install tomlkit
```

## Credits

Sensor integration and GUI updates by Martin Paz. Updates, devops by Daniel Dieser.

## License

Open Source

---

*Daniel Dieser -- Puerto Madryn, Patagonia, Argentina*
*Telegram: [@mrmoz33](https://t.me/mrmoz33)*
