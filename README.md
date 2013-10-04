spritesheet-tester
==================

Test a sprite sheet using a simple json file.

## Usage

Open `index.html` and add an entity to the url, e.g. `index.html?entity=entities/blob.json`.

Entities are defined in `json` documents.

```json
{
  "name": "Blob",
  "width": 310,
  "height": 290,
  "sprite": {
    "file": "images/blob.png",
    "width": 310,
    "height": 290,
    "animations": {
      "stationary": [[0,0, 300], [0,1, 300], [0,2, 300]],
      "leap": [[0,0, 150], [1,0, 150], [2,0, 150], [1,1, 200], [2,1, 200]]
    }
  }
}
```

 - `"name"` is shown at the top of the window
 - `"width"` and `"height"` at the top level are the size each cell will be drawn on the canvas (in pixels).
 - `"sprite"` describes the actual sprite sheet and any animations you want to see.
  - `"file"` is the path from index.html to the sprite sheet image file.
  - `"width"` and `"height"` within the sprite sheet defines how big each sprite tile is within the sprite sheet (only tiles of a single size are supported).
  - `"animations"` is a container for any animations you want to display. Name the animations anything you like, the name will be shown below the animation on the canvas.

An animation is an array of arrays. e.g. `[[0,0], [0,1, 200], [0,2]]` defines a 3-frame animation using the 3 images down the left-hand column of the sprite sheet. The first and third frames (`[0,0]` and `[0,2]`) have the default delay of 100ms, the second frame (`[0,1, 200]`) will be shown for 200ms.

Animations will be looped continuously.
