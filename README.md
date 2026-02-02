# Orders Mini Card

A visionOS-style orders widget rendered in a 3D room scene using Three.js.

**Live Preview:** https://jwzy.github.io/orders-mini-card/

## Summary of Important Prompts

The prompts below were used to build this project with Claude. Follow them in order to replicate the result.

### 1. Initial Widget Concept
> Build a 550x354pt visionOS-style glass widget with:
> - LEFT: Order count (large number), 7-day sparkline bar chart, % change badge
> - RIGHT: Live order feed (new orders push to top, old flow down)
> - Warm amber glass aesthetic with white edge highlights

### 2. 3D Environment
> Create a simple 3D room scene with Three.js:
> - Wall and floor
> - Widget mounted on wall using CSS3DRenderer
> - Minimal furniture (couch, TV cabinet, plant, rug)
> - Warm afternoon/sunset lighting from left

### 3. Camera Behavior
> Make the camera move with the mouse on hover instead of click-drag. Invert the tracking so it follows eye direction (look left, scene shifts right).

### 4. Typography Cleanup (NYC Subway Style)
> Simplify the left pane - it's too busy. Look at NYC subway poster design:
> - Only 2 font sizes (18px body, 72px for the big number)
> - Remove the % change badge
> - Change label to "Orders today"
> - All text full opacity (no dim colors)

### 5. Glass Effect Refinement
> Increase the transparency on the widget (22% opacity). The dark scrims look out of place - replace them with CSS mask-image fading instead.

### 6. Feed Polish
> - Add multicultural names with emoji flags
> - Orders come in every 1200-2400ms
> - Top alignment between left and right panels

## Tech Stack

- **Three.js** - 3D rendering
- **CSS3DRenderer** - HTML widget in 3D space
- **GLTFLoader / OBJLoader / MTLLoader** - 3D model loading
- **CSS backdrop-filter** - Frosted glass effect

## Local Development

```bash
cd docs
python3 -m http.server 8080
# Open http://localhost:8080
```

## Files

```
docs/
├── index.html          # HTML structure
├── styles.css          # Widget styling + glass effect
├── app.js              # Three.js scene + widget logic
├── Couch Medium.glb    # 3D models
├── Cabinet Television Doo.glb
├── Fiddle-leaf Plant.glb
├── Modern_Rug_01.obj
└── Modern_Rug_01.mtl
```
