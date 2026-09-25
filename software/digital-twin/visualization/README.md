# 3D Digital Twin Visualization & Operator Telemetry

This directory implements the 3D visual frontend and live operator dashboard for monitoring the machine's cyber-physical state.

## Components
- `model_viewer/`: WebGL / Three.js 3D viewer rendering the mechanical CAD model with dynamic joint rotations driven by telemetry.
- `dashboard/`: Real-time telemetry visualization showing live sensor charts, virtual stress heatmaps, and blade remaining useful life (RUL) gauges.
- `websocket_bridge.js`: Lightweight bridge broadcasting MQTT telemetry events to connected browser sessions.
