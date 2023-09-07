---
title: Custom Card "Scenes"
hide:
  - toc
---
<!-- markdownlint-disable MD046 -->

## Description

![example-image-light](../../assets/img/custom_card_andyblac_person/custom_card_andyblac_scenes_light.png)
![example-image-dark](../../assets/img/custom_card_andyblac_person/custom_card_andyblac_scenes_dark.png)

## Credits

- Authors:
    - AndyBlac

## Changelog

<details>
<summary>1.1.0</summary>
Initial release
</details>

## Variables

| Variable | Default | Required         | Notes             |
|----------|---------|------------------|-------------------|
| entity     |         | Yes | The scene entity |
| ulm_card_scene_color |       | No | This lets you chnage the colour if the icon and background. |

## Usage

```yaml
      - type: custom:button-card
        template: custom_card_andyblac_scenes
        entity: scene.good_morning
        variables:
          ulm_card_scene_color: yellow
```

??? note "Template Code"

    ```yaml title="custom_card_andyblac_scenes.yaml"
    --8<-- "custom_cards/custom_card_andyblac_scenes/custom_card_andyblac_scenes.yaml"
    ```
