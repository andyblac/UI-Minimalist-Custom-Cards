---
title: Custom Card "Status"
hide:
  - toc
---
<!-- markdownlint-disable MD046 -->

## Description

![example-image-light](../../assets/img/custom_card_andyblac_status/custom_card_andyblac_status_light.png)
![example-image-dark](../../assets/img/custom_card_andyblac_status/custom_card_andyblac_status_dark.png)

## Credits

- Authors:
    - AndyBlac

## Changelog

<details>
<summary>1.3</summary>
Initial release
</details>

## Variables

| Variable | Default | Required         | Notes             |
|----------|---------|------------------|-------------------|
| entity   |         | Yes              | The status entity |
| name		 | friendly_name | No         | Name of the state sensor |
| tap_action | Card: more-info | No	    | The action to perform when tapping in card area |
| hold_action |      | No	              | The action to perform when tapping in card area|
| navigation_path    |                  | Yes | This is required when using 'navigate' for action type |
| ulm_custom_card_andyblac_status_color_on |  | No | This lets you change the colour of the icon and background, when state is 'on' |
| button   |         | No               | Use this to add icon actions |
| icon		 | sensor icon   | No	        | The icon to show |
| tap_action | Icon: more-info  | No     |  The action to perform when tapping on icon |
| hold_action | Icon: more-info  | No   |  The action to perform when tapping on icon |

## Usage

```yaml
- type: custom:button-card
  name: Heating
  entity: sensor.security_state
  template:
    - custom_card_andyblac_status
  tap_action:  # this is for the card action.
    action: more-info
  variables:
    ulm_custom_card_andyblac_status_color_on: blue
    button:
      icon: mdi:shower
      tap_action:
        action: navigate
        navigation_path: bathroom
```

??? note "Template Code"

    ```yaml title="custom_card_andyblac_status.yaml"
    --8<-- "custom_cards/custom_card_andyblac_scenes/custom_card_andyblac_status.yaml"
    ```
