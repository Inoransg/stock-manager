# Singapore, in miniature

An interactive 3D model of Marina Bay, built from three.js geometry with no external models,
textures or API keys. All landmarks, the skyline, trees, water and lighting are generated in code.

## Run it

The whole experience is one file, `index.html`. three.js r160 is loaded from the jsDelivr CDN
through an import map, so you need an internet connection and a modern browser (WebGL 2 and
import maps: Chrome/Edge 89+, Firefox 108+, Safari 16.4+).

ES modules don't load from `file://`, so serve the folder over HTTP:

```sh
cd singapore-miniature
npx serve .            # or: python3 -m http.server 8000
```

Then open the printed URL (for example http://localhost:3000 or http://localhost:8000).

## Controls

| Action | Mouse / keyboard | Touch |
| --- | --- | --- |
| Orbit | Left-drag | One-finger drag |
| Zoom | Scroll, or `+` / `-` with the model focused | Pinch |
| Pan | Right-drag, Shift-drag, or arrow keys | Two-finger drag |
| Select a landmark | Click it or its label | Tap it or its label |

- **Landmarks** opens an accessible list of every landmark. Use it to explore by keyboard.
- **Day / Sunset / Night** switches the sky, sun, water, windows and landmark lighting.
- **Guided tour** flies through eight landmarks. Dragging, zooming or picking a landmark ends it.
- **Reset view** returns to the opening view of the bay.
- **Reduce motion** makes camera moves instant and stops ambient animation. It starts on if your
  system asks for reduced motion.
- `Esc` closes the list, ends the tour, or goes back to the city.

## Notes

- Geography and proportions are stylized. Landmarks are exaggerated in scale so they read clearly.
- If WebGL is unavailable or the CDN can't be reached, the page says so and keeps the landmark
  guide working without the 3D view.
