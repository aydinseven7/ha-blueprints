# Home Assistant IKEA BILRESA Blueprints

Custom automation blueprints for IKEA BILRESA Matter devices with Matter over Thread support.

## Blueprints

### 1. IKEA BILRESA E2489 Dual Button

**Source:** [Censay/haos-blueprints](https://raw.githubusercontent.com/censay/haos-blueprints/refs/heads/master/ikea-bilresa-e2489-matter-smart-button/ikea-bilresa-e2489-matter-smart-button.yaml) (modified)
**Version:** v1.1.0  
**Last Updated:** 2026-02-27

#### Capabilities
- Single press, double press, and long press (on press/release) detection
- Two independent button channels
- Support for any Home Assistant action (scenes, scripts, automations, etc.)
- Prevents re-triggering on Matter server reboot via availability state filtering

#### Import
[![Import Dual Button Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/create-automation/?blueprint_url=https://raw.githubusercontent.com/aydinseven7/ha-blueprints/main/home-assistant/blueprints/bilresa-dual-button.yaml)

**Direct Link:**
```
https://my.home-assistant.io/create-automation/?blueprint_url=https://raw.githubusercontent.com/aydinseven7/ha-blueprints/main/home-assistant/blueprints/bilresa-dual-button.yaml
```

---

### 2. IKEA BILRESA Scroll Wheel

**Source:** [jhol-byte](https://gist.githubusercontent.com/jhol-byte/b2731a4d2476f530d76b9ff409f7f3a4/raw/a71e9a61a8257e7449fc779b9c4b2d9834639f1b/Ikea_bilresa_scroll_wheel.yaml) (modified)  
**Version:** 2026-03-22  

#### Capabilities
- Three independent channels (Channel 1, 2, 3)
- Per-channel button actions: single click, double-click, triple-click, long press, hold
- Per-channel scroll wheel modes:
  - Light dimming
  - Color temperature control
  - Color hue control
  - Media player volume control
  - Dynamic mode (choose via input_select)
  - User-defined mode with exposed variables
- Global settings for light and media player behavior
- Prevents re-triggering on Matter server reboot via availability state filtering
- Supports both "relaxed" (batched) and "instant" (real-time) scroll evaluation modes

#### Import
[![Import Scroll Wheel Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/create-automation/?blueprint_url=https://raw.githubusercontent.com/aydinseven7/ha-blueprints/main/home-assistant/blueprints/bilresa-scroll-wheel.yaml)

**Direct Link:**
```
https://my.home-assistant.io/create-automation/?blueprint_url=https://raw.githubusercontent.com/aydinseven7/ha-blueprints/main/home-assistant/blueprints/bilresa-scroll-wheel.yaml
```

---

## Setup Requirements

1. **Matter Integration**: Ensure Home Assistant's Matter integration is configured and discovery is enabled
2. **Thread Network**: BILRESA devices require an active Thread border router (e.g., Apple Home Hub, HomePod mini, Nanoleaf controller)
3. **Device Pairing**: Pair the BILRESA device to Home Assistant via Matter

## Configuration Notes

### For Scroll Wheel Blueprint
- **Event Entities**: You must enable the 9 hidden sensor entities on the BILRESA device for "instant" mode scroll evaluation
- **Scroll Evaluation Modes**:
  - **Relaxed**: Batches scroll clicks into a single action (1-8 clicks per batch)
  - **Instant**: Sends action calls in real-time for smooth control
- **Light Transition**: Default 0.5s for smooth transitions

### Availability Filtering
Both blueprints include protection against re-triggering when the Matter server reboots or devices become temporarily unavailable. This prevents unwanted automation executions during device discovery.

## Troubleshooting

**Blueprint not appearing after import?**
- Clear browser cache and reload Home Assistant
- Check that the blueprint YAML file is accessible at the import URL

**Scroll wheel not responding?**
- Verify event entities are correctly selected
- For "instant" mode, ensure hidden sensor entities are enabled in device settings
- Check Home Assistant logs for automation errors

**Repeated actions on reboot?**
- Availability filtering is active; if still occurs, verify trigger conditions in automation editor

## Community Credits

- Original Scroll Wheel Blueprint: [Home Assistant Community](https://community.home-assistant.io/t/ikea-bilresa-scroll-wheel-blueprint-matter/965365)
- Original Dual Button Blueprint: [censay (GitHub)](https://github.com/censay/haos-blueprints)

---

## Quick Links

- [IKEA BILRESA E2489 on IKEA.com](https://www.ikea.com/gb/en/p/bilresa-remote-control-80568192/)
- [Home Assistant Matter Documentation](https://www.home-assistant.io/integrations/matter/)
- [Home Assistant Blueprint Documentation](https://www.home-assistant.io/docs/automation/using_blueprints/)
