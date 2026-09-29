# VoxOne Showcase

### The Agent Voice Endpoint for the SCubeLabs Platform

**VoxOne** is the endpoint layer for the SCubeLabs voice experience: a cross-platform direction for browser-based WebRTC calling and an installable desktop softphone while keeping provider- and protocol-specific behavior outside the UI.

This public repository documents the product architecture, interaction model, call-control boundaries, demonstrations, and engineering evidence. The implementation remains separated from the showcase surface.

## Architectural direction

```text
User Experience
      │
      ▼
Call Control Core
      │
      ▼
Connection / Protocol Adapters
      │
      ├── SIP over WebSocket
      ├── WebRTC media
      └── Native SIP for desktop
      │
      ▼
SCubeLabs Signaling & Media Infrastructure
```

The React/UI layer should operate on canonical call concepts rather than SIP-specific transactions or provider APIs.

## Canonical call model

`CallSession` · `CallLeg` · `EndpointIdentity` · `Connection` · `MediaSession` · `Device` · `CallState` · `CallEvent` · `Account` · `Registration`

## Engineering goals

- One coherent call-control model across browser and desktop.
- Protocol/provider behavior isolated behind adapters.
- Explicit call and media state transitions.
- Diagnostic visibility suitable for serious telephony troubleshooting.
- Clean integration with SCubeLabs agent, realtime, voice-edge and media domains.
- Evidence-driven interoperability and failure testing.

## Status

The showcase represents the public architecture and demonstration surface for VoxOne. Capability claims should be tied to executable evidence as the implementation progresses.

[Explore the SCubeLabs platform](https://github.com/scubelabs/scubelabs)
