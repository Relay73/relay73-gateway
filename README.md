# Relay73 Gateway

Multi-modem gateway software for the **Relay73** amateur-radio ecosystem.

> **Status:** Repository scaffold. Existing Windows RMS gateway development and attended test-node software have not yet been migrated into this repository.

## Purpose

A single station may support more than one digital modem. Relay73 Gateway is intended to coordinate those modems without requiring the operator to manually choose between entirely separate gateway setups.

## Planned responsibilities

- Start, stop, monitor, and recover configured modem services.
- Integrate with RMS Packet / Winlink gateway workflows where supported.
- Advertise available modem capabilities to a central directory when enabled.
- Coordinate access to shared audio and PTT hardware.
- Surface useful health, RF state, logging, and diagnostics information.
- Preserve independently operating modem implementations.

## Existing development context

Development prototypes include a Windows controller for RMS Packet, official VARA FM, and Modem73 KISS integration. A gateway can support official VARA FM and Modem73 concurrently, with careful arbitration of access to one radio.

**Important:** Official VARA FM support is distinct from any retired research or compatibility experiments. This project does not redistribute proprietary modem binaries.

## Design boundaries

- Radio ownership and PTT arbitration must prevent conflicting transmissions.
- Host/modem processes need bounded startup, shutdown, and reconnect behavior.
- The directory is an optional discovery aid, not a requirement to provide local gateway service.
- Upstream Modem73 should stay updateable without a heavily modified fork.
- An RF transport ACK alone is not proof of Winlink/CMS delivery.

## Initial milestones

1. Migrate the gateway controller and supported host bridges.
2. Document installation, first-run configuration, and unattended startup.
3. Stabilize Modem73 KISS and official VARA FM service handling.
4. Add structured capability reporting for [relay73-directory](https://github.com/Relay73/relay73-directory).
5. Validate behavior under failed starts, disconnects, and RF impairments.

## Related repositories

[Project hub](https://github.com/Relay73/Relay73) | [Modem adapters](https://github.com/Relay73/relay73-modem-adapters) | [RF lab](https://github.com/Relay73/relay73-rf-lab)

Build, installation, licensing, and operator instructions will be expanded as implementation is migrated.
