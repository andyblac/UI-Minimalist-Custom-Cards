---
title: Room Card
hide:
  - toc
---
<!-- markdownlint-disable MD046 -->

## Description

![example-image-light](../../assets/img/custom_card_andyblac_room/custom_card_andyblac_room_light.png)
![example-image-dark](../../assets/img/custom_card_andyblac_room/custom_card_andyblac_room_dark.png)

This is the `room-card`, used to show the state of single room in a quick glance.
The card has support for up to 4 subicons at the right side of the card, and 6 sensor subicons going around the inside of the room icon. These can be configured using custom colors and tap actions.

## Credits

- Authors:
    - AndyBlac
- Full credit to the Minimalist UI team for creating the base card that this 'mod' was used.

## Changelog

<details>
<summary>2.0</summary>
Initial release
</details>

## Room Variables

| Variable                                           | Default         | Required    | Notes          | Requirement |
|----------------------------------------------------|-----------------|-------------|----------------|-------------|
| ulm_custom_card_andyblac_room_use_small_label_font | `false`         | No          | My card uses slightly larger fonts than the original card, to use use the orignal card font size set this to `true` |
| ulm_custom_card_andyblac_room_use_label_icons      | `false`         | No          | This option lets you see an icon next to the text of the sensor_label information (🌡️ / 💧 / 🔆 )
| ulm_custom_card_andyblac_room_color                | `theme`         | No          | This lets you set the room colour.</br>You can use any colour in your theme that uses the following naming structure `color-red: "241, 139, 130"` or `color-yellow: "252, 214, 99"`</br>So for example `color-background-purple: "var(--color-purple)"` in your theme, you would ignore the text `color-` and just set `background-purple`
| sensor_label_1                                     |                 | No          | The enitiy_id of a sensor you wish to display the state of |  |
| sensor_label_2                                     |                 | No          | The enitiy_id of a sensor you wish to display the state of |  |
| sensor_label_3                                     |                 | No          | The enitiy_id of a sensor you wish to display the state of |  |
| entity_1                                           |                 | No          | a `room_entity` object (see below) |  |
| entity_2                                           |                 | No          | a `room_entity` object (see below) |  |
| entity_3                                           |                 | No          | a `room_entity` object (see below) |  |
| entity_4                                           |                 | No          | a `room_entity` object (see below) |  |
| sensor_1                                           |                 | No          | a `sensor` object (see below) |  |
| sensor_2                                           |                 | No          | a `sensor` object (see below) |  |
| sensor_3                                           |                 | No          | a `sensor` object (see below) |  |
| sensor_4                                           |                 | No          | a `sensor` object (see below) |  |
| sensor_5                                           |                 | No          | a `sensor` object (see below) |  |
| sensor_6                                           |                 | No          | a `sensor` object (see below) |  |

## Room object

| Variable                               | Default         | Required    | Notes          | Requirement |
|----------------------------------------|-----------------|-------------|----------------|-------------|
| entity_id                              |                 | No          | The entity_id of the widget to control | |
| icon                                   |                 | No          | Allows you set an icon of your choice | |
| templates                              |                 | No          | List of the additional button card templates to apply to this icon | |
| tap_action                             |                 | No          | tap_action for the icon (see button card documentation for options) |  |
| hold_action                            |                 | No          | hold_action for the icon (see button card documentation for options) |  |

## Sensor object

| Variable                               | Default         | Required    | Notes          | Requirement |
|----------------------------------------|-----------------|-------------|----------------|-------------|
| entity_id                              |                 | No          | The entity_id of the sensor | |
| icon                                   |                 | No          | Allows you set an icon of your choice | |
| templates                              |                 | No          | List of the additional button card templates to apply to this icon | |
| tap_action                             |                 | No          | tap_action for the icon (see button card documentation for options) |  |
| hold_action                            |                 | No          | hold_action for the icon (see button card documentation for options) |  |

## Sensor Variables

| Variable                                        | Default         | Required    | Notes          | Requirement |
|-------------------------------------------------|-----------------|-------------|----------------|-------------|
| ulm_custom_card_andyblac_room_sensor_color      | Room colour     | No          | Allows you to change the color of the sensor color of state is `off` |
| ulm_custom_card_andyblac_room_sensor_color_on   | Room colour     | No          | Allows you to change the color of the sensor color of state is `on`  |


## Default card options

All the options from the button card are still available for the large room card.
If you want to tweak this card a little bit more, below are some examples. The full list can be found here: [link](https://github.com/custom-cards/button-card#main-options)

| Options                                | Default         | Required         | Notes          | Requirement |
|----------------------------------------|-----------------|------------------|----------------|-------------|
| entity                                 |                 | No | The entity_id for the large card | |
| icon                                   |                 | No | Icon to display. Defaults to the entity icon | |
| tap_action                             | navigate        | No | Define the type of action on click, if undefined, toggle will be used.</br>See [Action](https://github.com/custom-cards/button-card#Action)| |
| hold_action                            |                 | No | Define the type of action on hold, if undefined, nothing happens</br> See [Action](https://github.com/custom-cards/button-card#Action)| |
| label                                  |                 | No | Change the label text | |
| title                                  |                 | No | Change the title text | |

## Usage

```yaml
  - type: custom:button-card
    template:
      - custom_card_andyblac_room
    name: "Bathroom"
    tap_action:
      action: navigate
      navigation_path: bathroom
    variables:
      ulm_custom_card_andyblac_room_color: blue
      sensor_label_1: sensor.bathroom_humidity_sensor_temperature
      sensor_label_2: sensor.bathroom_humidity_sensor_humidity
      sensor_label_3: sensor.bathroom_humidity_derivative
      sensor_1:
        entity_id: input_boolean.hot_water_toggle
        tap_action:
          action: toggle
      entity_3:
        entity_id: light.bathroom_light
        ulm_custom_card_andyblac_room_icon_color_on: yellow
      entity_4:
        entity_id: fan.bathroom_extractor
        ulm_custom_card_andyblac_room_icon_color_on: blue
```

??? note "Template Code"

    ```yaml title="card_room.yaml"
    --8<-- "custom_cards/custom_card_andyblac_room/custom_card_andyblac_room.yaml"
    ```
