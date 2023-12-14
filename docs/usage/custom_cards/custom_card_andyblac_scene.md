---
title: Custom Card "Scene"
hide:
  - toc
---
<!-- markdownlint-disable MD046 -->

## Description

![example-image-light](../../assets/img/custom_card_andyblac_scene/custom_card_andyblac_scene_light.png)
![example-image-dark](../../assets/img/custom_card_andyblac_scene/custom_card_andyblac_scene_dark.png)

This card let you activate a scene by tapping on the icon, it also gives last activated information.

## Credits

- Authors:
    - AndyBlac

## Changelog

<details>
<summary>1.1</summary>
Initial release
</details>
<details>
<summary>1.2</summary>
Add ability to have actions on the icon and the card.
</details>
<details>
<summary>1.3</summary>
Fix card info text layout, and add unavailable indicator.
</details>
<details>
<summary>1.4</summary>
add support for custom colours by using `rgb()`
</details>

## Variables

| Variable                             | Default | Required    | Notes                                                       |
|--------------------------------------|---------|-------------|-------------------------------------------------------------|
| entity                               |         | Yes         | The scene entity                                            |
| ulm_custom_card_andyblac_scene_color |         | No          | This lets you change the colour of the icon and background. |

## Usage

For the colour, you can use any colour in your theme that uses the following naming structure `color-red: "241, 139, 130"` or `color-yellow: "252, 214, 99"`,</br>
so for example `color-background-purple: "var(--color-purple)"` in your theme, you would ignore the text `color-` and just set `background-purple`,</br>
you can also use custom colours by using for example `rgb(255,0,0)`

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
