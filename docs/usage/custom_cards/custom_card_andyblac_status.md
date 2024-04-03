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
<details>
<summary>1.4</summary>
add support for custom colours by using `rgb()`
</details>
<details>
<summary>1.4.1</summary>
tweak entity error icon colour, so it matches the system default
</details>
<details>
<summary>1.5</summary>
fix state to show precision set
add support for low/med/high status colours
add support for 3 status value colours
</details>

## Variables

| Variable                                             | Default     | Required  | Notes                                                                                                 |
|------------------------------------------------------|-------------|-----------|-------------------------------------------------------------------------------------------------------|
| entity                                               |             | Yes       | The status entity                                                                                     |
| ulm_custom_card_andyblac_status_color_on             |             | No        | This lets you change the colour of the icon and background, when state is 'on'                        |
| ulm_custom_card_andyblac_status_color_low_value      |             | No        | This lets you enable the low color state, enter the value for the color if it falls below this value  |
| ulm_custom_card_andyblac_status_color_high_value     |             | No        | This lets you enable the high color state, enter the value for the color if it rises above this value |
| ulm_custom_card_andyblac_status_color_low            | `green`     | No        | The color used for the lower state value                                                              |
| ulm_custom_card_andyblac_status_color_medium         | `yellow`    | No        | The color use when the state value is between the lower and higher set pionts                         |
| ulm_custom_card_andyblac_status_color_high           | `red`       | No        | The color for the lower state value                                                                   |
| ulm_custom_card_andyblac_status_color_state_1_value  |             | No        | This lets you change the colour, when the state equals this value                                     |
| ulm_custom_card_andyblac_status_color_state_2_value  |             | No        | This lets you change the colour, when the state equals this value                                     |
| ulm_custom_card_andyblac_status_color_state_3_value  |             | No        | This lets you change the colour, when the state equals this value                                     |
| ulm_custom_card_andyblac_status_color_state_1        | `blue`      | No        | The color used for the state_1 state value                                                            |
| ulm_custom_card_andyblac_status_color_state_2        | `green`     | No        | The color used for the state_2 state value                                                            |
| ulm_custom_card_andyblac_status_color_state_3        | `red`       | No        | The color used for the state_3 state value                                                            |
| button                                               |             | No        | The button object (see below)                                                                         |

## Button object

| Variable                                 | Default     | Required  | Notes                                                                          |
|------------------------------------------|-------------|-----------|--------------------------------------------------------------------------------|
| icon		                                 |             | No	       | The icon to show, Defaults to the entity icon                                  |
| tap_action                               | `more-info` | No        | Define the type of action on click, if undefined, toggle will be used.</br>See [Action](https://github.com/custom-cards/button-card#Action) |
| hold_action                              | `more-info` | No        | Define the type of action on hold, if undefined, nothing happens</br> See [Action](https://github.com/custom-cards/button-card#Action) |

## Default card options

| Options                                  | Default         | Required         | Notes                      |
|------------------------------------------|-----------------|------------------|----------------------------|
| entity                                   |                 | No               | The entity_id for the card |
| name                                     |                 | No               | Change the title text      |
| state_display                            |                 | No               | Change the label text.     |

## Usage

For the colour, you can use any colour in your theme that uses the following naming structure `color-red: "241, 139, 130"` or `color-yellow: "252, 214, 99"`,
so for example `color-background-purple: "var(--color-purple)"` in your theme, you would ignore the text `color-` and just set `background-purple`,
you can also use custom colours by using for example `rgb(255,0,0)`

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
        action: navigate # this is for the button action.
        navigation_path: bathroom
```

??? note "Template Code"

    ```yaml title="custom_card_andyblac_status.yaml"
    --8<-- "custom_cards/custom_card_andyblac_status/custom_card_andyblac_status.yaml"
    ```
