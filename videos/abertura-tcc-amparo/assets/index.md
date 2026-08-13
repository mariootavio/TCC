# assets · 2 sourced

| role | frozen path | provenance |
|---|---|---|
| logo (symbol-only, unused in final build) | `.media/images/logo_001.svg` | user-supplied — ingested via `media-use resolve --type logo --from brand/LogoAmparo.svg` (original: `/Users/mariootavio/Desktop/TCC/brand/LogoAmparo.svg`, locked brand asset, never redrawn) |
| lockup (symbol + "Amparo" wordmark, used in final build) | `.media/images/lockup_white.png` | derived from user-supplied `/Users/mariootavio/Desktop/TCC/brand/LogoAmparo-SemFundo.png` (locked brand asset) via alpha-channel-preserving recolor to solid `#FFFFFF` (Pillow: split alpha, fill white, reapply alpha — no CSS filter, no fringing, geometry/proportions/anti-aliasing identical to source). Content-cropped to bbox (192,173)-(843,784) of the original 1024×1024 canvas. |
