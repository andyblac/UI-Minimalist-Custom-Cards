---
title: Custom Card "Scene"
hide:
  - toc
---
<!-- markdownlint-disable MD046 -->

## Description

![example-image-light](../../assets/img/custom_card_andyblac_scene/custom_card_andyblac_scene_light.png)
![example-image-dark](../../assets/img/custom_card_andyblac_scene/custom_card_andyblac_scene_dark.png)

## Credits

- Authors:
    - AndyBlac

## Changelog

<details>
<summary>1.1.0</summary>
Initial release
<summary>1.2.0</summary>
Add ability to have actions on the icon and the card.
<summary>1.3.0</summary>
Fix card info text layout, and add unavailable indicator.
</details>

## Variables

| Variable | Default | Required         | Notes             |
|----------|---------|------------------|-------------------|
| entity   |         | Yes              | The scene entity  |
| ulm_custom_card_andyblac_scene_color |  | No | This lets you change the colour of the icon and background. |

## Usage

```yaml
      - type: custom:button-card
        template: custom_card_andyblac_scene
        entity: scene.good_morning
        variables:
          ulm_card_scene_color: yellow
```

??? note "Template Code"

    ```yaml title="custom_card_andyblac_scenes.yaml"
    --8<-- "custom_cards/custom_card_andyblac_scenes/custom_card_andyblac_scenes.yaml"
    ```
