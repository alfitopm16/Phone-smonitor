# 📱 Phone SMonitor

### Local Wi-Fi Telemetry & Device Monitoring for Android

Phone SMonitor is an Android application designed to monitor the real-time hardware status of one Android device from another device over a **local Wi-Fi or hotspot network**.
The application uses a **server-client architecture** where the monitored device runs a lightweight local HTTP server, while another device acts as a monitoring dashboard.
No cloud server is required.

## ✨ Overview

PhoneLink Monitor allows users to monitor important device telemetry such as:
- Battery percentage
- Charging status
- Battery temperature
- Voltage
- Current
- Power consumption
- CPU temperature
- GPU temperature (when supported)
- Thermal status
- Device connection status

All communication takes place directly between the devices through a local network.

### Architecture
┌─────────────────────────────┐
│          PHONE 1            │
│      Monitored Device       │
│                             │
│  Android Hardware APIs      │
│          ↓                  │
│   Telemetry Collector       │
│          ↓                  │
│    Local HTTP Server        │
│       Port: 8080            │
└─────────────┬───────────────┘
              │
              │ Local Wi-Fi /
              │ Mobile Hotspot
              │
              ↓
┌─────────────────────────────┐
│          PHONE 2            │
│     Monitoring Device       │
│                             │
│      HTTP Client            │
│          ↓                  │
│   Telemetry Processor       │
│          ↓                  │
│    Monitoring Dashboard     │
└─────────────────────────────┘
