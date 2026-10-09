**Project description**
Live page [https://local.me.muz.li/oaviv/dispersion-2](https://me.muz.li/oaviv/dispersion-2)
A live study of how glass splits white light. Every pixel is computed in real time by a single WebGL2 fragment shader.

Built from scratch. There's no three.js, Babylon or any other 3D or WebGL library, and no framework or build step. The page loads no images, models or textures; everything you see is generated in the browser. The whole site is one 39 KB HTML file, about 15 KB over the wire. The scene is a roughly 270-line shader drawn in a single draw call per frame, with no post-processing passes. The only outside request is the web font.

**The glass.**
Each shape is a mathematical distance field: a liquid drop, a lens, a prism, a brilliant-cut gem and a faceted crystal. Scrolling blends one field into the next, so the object morphs between them. The droplet that follows your cursor is a second field merged into the first with a smooth minimum, which makes it pull away and rejoin like liquid.

**The light.**
Rays are marched into the glass and bent with Snell's law. When a ray can't escape, it bounces off the inner faces, as it does inside a cut diamond. It then exits at seven separate wavelengths between 400 and 700 nm. Each wavelength gets its own refractive index from a Cauchy fit to the material's real index and Abbe number, and the seven are blended back into color. That is why the edges show smooth spectra rather than simple RGB splitting. The dispersion is drawn three times stronger than life so it reads on screen.

**The type.**
The headline isn't laid over the glass. It's painted onto the wall behind it, so you see it through the glass, magnified, flipped and fringed with color.

**Shadow and caustics.**
Rays traced from the wall toward the light pass through the same distance field. That gives a soft shadow and a bright, color-edged core where the glass focuses light.

**The crystal.**
A 3D Voronoi pattern gives each micro-facet its own tilt, so the stage lights sparkle across it differently as it turns. Its reflection in the floor is traced, not mirrored, and the glow around it comes from the same shader rather than a separate bloom pass.

**Real materials.**
Water, N-BK7 crown glass, N-SF11 flint, diamond and quartz use their published optical constants. A live readout tracks them as you scroll, and a playground lets you set your own index and Abbe number.

The page adapts its resolution to hold the frame rate, supports light and dark mode, and respects reduced-motion settings. The footer shows your live frame rate and GPU.
