# Neon Cyberpunk City

## Project Overview

Neon Cyberpunk City is an interactive 3D environment built using pure WebGL, without the use of external libraries or CDNs. The project features a procedurally generated city with dynamic lighting, particle effects, and a comprehensive menu system for real-time customization.

## Key Features

- **Procedural Generation**: A city layout featuring over 120 unique buildings generated algorithmically.
- **Dynamic Environment**: Day/night cycle with an optional automatic transition mode.
- **Visual Customization**: Real-time adjustment of neon intensity, fog density, particle effects, and color vibrance.
- **Predefined Themes**: Multiple visual styles including NVIDIA Green, Magenta Pulse, Ocean Cyan, Sunset Neon, and Rainbow Market.
- **Interactive UI**: Functional menu system for navigation and settings adjustment.
- **Animated Billboard**: A central welcome billboard featuring scrolling text.
- **Facade Advertisements**: Procedurally placed banner advertisements on building exteriors.
- **Urban Simulation**: Traffic simulation with moving vehicles, pedestrian agents, and overhead drones.
- **Camera Controls**: Support for both First-Person (FPS) and Orbit camera modes.
- **Debug Tools**: Wireframe toggle for visual debugging and effect analysis.
- **Media Capture**: Built-in screenshot functionality.

## Controls

### Orbit Mode

- **Rotate**: Click and drag the mouse.
- **Zoom**: Use the scroll wheel.

### FPS Mode

- **Movement**: WASD keys.
- **Ascend**: Space key.
- **Descend**: Ctrl key.

### General Interaction

- **Menu**: Click to interact with UI elements.
- **Camera Switch**: Toggle between Orbit and FPS modes via the menu.

## Customization Guide

### Adding Custom Banners

1. Create a directory named `assets/` in the project root.
2. Place banner images (PNG format recommended) within this directory.
3. Update the `bannerDefs` array in the JavaScript source:

```javascript
const bannerDefs = [
  { name: "Your Banner Name", fallback: "TEXT FALLBACK" },
  // Add more banners here
];
```

The system automatically attempts to load `assets/your-banner-name.png` (converted to lowercase, spaces removed). If the image fails to load, the specified fallback text will be displayed.

### Adjusting the Welcome Billboard

The dimensions and position of the welcome billboard can be modified by adjusting the following variables:

```javascript
const wWelcome = 12.0; // Width
const hWelcome = 3.0; // Height
const welcomePos = [0, 12, 0]; // Position [x, y, z]
```

### Theme Customization

New visual themes can be added to the `THEMES` object:

```javascript
const THEMES = {
  yourtheme: { accent: [r, g, b], paint: [r, g, b] },
  // Add more themes here
};
```

## Technical Specifications

- **Rendering Engine**: Pure WebGL (no Three.js or other frameworks).
- **Architecture**: Single HTML file containing all logic, styles, and shaders.
- **Dependencies**: Zero external dependencies.
- **Texture Generation**: Procedural textures generated via HTML Canvas.
- **Shaders**: Custom GLSL shaders for lighting, fog, and post-processing effects.
- **Asset Management**: Asynchronous image loading for banner assets.

## Performance Optimization

- **Image Resolution**: Banner images should be 256x128 pixels or smaller to minimize memory usage.
- **Particle Count**: Reduce the particle count in settings if experiencing low frame rates.
- **Visual Effects**: Lowering fog and neon intensity can improve performance on older hardware.

## Browser Compatibility

This project is compatible with all modern web browsers that support WebGL, including:

- Google Chrome
- Mozilla Firefox
- Apple Safari
- Microsoft Edge

Developed as a pure WebGL technical demonstration.
