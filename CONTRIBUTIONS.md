# Contributing to JSX Clipscript

Thank you for your interest in contributing to **JSX Clipscript** ([https://clipscript.jsxcreatives.com](https://clipscript.jsxcreatives.com)), maintained by **[JSX Creatives](https://www.jsxcreatives.com)**.

This document outlines the standards, recipe schema, and submission workflow for adding new production prompt scripts, camera motion rigs, or studio templates to the library.

---

## 1. Core Principles

1. **Copy-Ready Formulas:** Every `template_prompt` must use explicit parenthetical reference hooks so creators know immediately where to bind their assets:
   - `(the character from the reference image)`
   - `(the product from the reference image)`
   - `(the outfit from the reference image)`
   - `(the environment from the reference image)`
   - `(the input reference video)`
2. **Engine Compatibility:** Specify accurate model routing (`image_model` for frame-0 keyframe conditioning and `video_model` for motion generation across Seedance, Kling, Wan, Veo, MiniMax, or ComfyUI).
3. **Clean Documentation:** Do not include emojis, personal local filesystem paths, API keys, or proprietary third-party brand watermarks in markdown or JSON files.

---

## 2. Studio Sections

New recipes must be assigned to one of the 10 standard studio sections:

- `Marketing Studio & Ads (UGC, E-commerce, TV)`
- `Camera & Motion Control (Kling, Seedance, MiniMax, Wan, Veo)`
- `AI Influencer & Character System`
- `Apps, AI Employees & Prompt Director Skills`
- `Katana (Commercial & Product Presets)`
- `Cinema Studio (Directorial & Cinematic Sequences)`
- `Viral & Effects (Camera Moves, Hub Effects)`
- `Mixed Media & Reels Studio (Collage, Kinetic Type, V2V)`
- `Explainer & Animation Styles`
- `Genjutsu (Video Multiplier & Replacement)`

---

## 3. Recipe JSON Schema

Each entry in `ALL-CLIPSCRIPT-RECIPES.json` follows this exact structure:

```json
{
  "id": "studio-unique-slug",
  "name": "Recipe Title (Subcategory Label)",
  "section": "Cinema Studio (Directorial & Cinematic Sequences)",
  "subcategory": "Cinema 4.0 Camera Movements",
  "visible_effect": "Concise one-sentence summary of the visual motion, lighting, or transition effect.",
  "preview_video_url": "https://.../preview.mp4",
  "preview_image_url": "https://.../keyframe.webp",
  "model_routing": {
    "image_model": "Soul 2.0 / Nano Banana Pro",
    "video_model": "Seedance 2.0 / Kling 2.6"
  },
  "template_prompt": "Cinematic widescreen sequence in (the environment from the reference image) featuring (the character from the reference image).\n\n- Camera Movement: ...\n- Preserve exact facial geometry, wardrobe textures, and environmental continuity across the shot.",
  "example_prompt": "Literal example prompt used to generate the sample output.",
  "keyframe_step": "Frame-0 conditioning instructions for anchoring the subject and environment.",
  "video_motion_step": "Motion diffusion and camera trajectory instructions.",
  "negative_prompt": "flickering, morphing faces, warped text, unstable horizon, watermark",
  "settings": {
    "aspect_ratio": "16:9 / 9:16",
    "duration": "5s–10s"
  },
  "reference_video_url": null
}
```

---

## 4. Pull Request Checklist

Before submitting a pull request:

1. Validate that `ALL-CLIPSCRIPT-RECIPES.json` parses with zero JSON syntax errors and contains no duplicate `id` values.
2. Synchronize `ALL-CLIPSCRIPT-RECIPES.md` and the embedded `recipes` array in `index.html`.
3. Verify that all embedded JavaScript in `index.html` parses cleanly (`node -e "new (require('vm').Script)(...)"`).
4. Ensure zero emojis, zero local machine paths, and zero credentials exist in any staged file.

---

## 5. Contact & Attribution

All contributions are released under the [MIT License](LICENSE).  
For studio inquiries or custom generative pipeline engineering, contact **JSX Creatives** at `js@jsxcreatives.com` or visit [https://www.jsxcreatives.com](https://www.jsxcreatives.com).
