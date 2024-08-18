# shadowRendering

Aim of this folder is to understand the side-effects of various combinations of `<renderingAttribute name="shadowRendering" .../>` and `strokeWidth` definitions.

## Results

The rendering result is as expected if a lien is visible for primary highways that varies in width with zoom level according to the specified values.
There is no shadow to be expected with the given configuration. The effect of the sole presence of the `shadowRendering` attribute is tested.

| Renderer | side_effect.render.xml | side_effect_shadowRendering.render.xml | attrFloatValue.render.xml | attrFloatValue_shadowRendering.render.xml | attrIntValue.render.xml | attrIntValue_shadowRendering.render.xml | attrCombined.render.xml | attrCombined_shadowRendering.render.xml |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| OsmAndMapCreator 3.0 | ✅ | ❓ line has constant width (likely `strokeWidth="1"`) | ❌ nothing to be seen | ❓ line has constant width (likely `strokeWidth="1"`) | ✅ | ✅| ✅ | ✅|
| OsmAnd 4.7.17 Renderer Version 1 | ❓ line is there and scales (?), but old renderings of the line stay on screen cluttering everything | ❓ line is there and scales (?), but old renderings of the line stay on screen  cluttering everything. Some jitter. | ❌ nothing to be seen | ❓ line is there and scales (?), but old renderings of the line stay on screen cluttering everything | ❓ line is there and scales (?), but old renderings of the line stay on screen  cluttering everything. Some jitter. | ❓ line is there and scales (?), but old renderings of the line stay on screen cluttering everything |
| OsmAnd 4.7.17 Renderer Version 2 (OpenGL) | ❌ nothing to be seen + crashes sometimes | ❌ nothing to be seen | ✅ | ✅ | ❌ nothing to be seen | ❌ nothing to be seen |
