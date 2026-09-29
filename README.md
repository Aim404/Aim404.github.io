# Yuncong Yang — personal homepage

Source for <https://aim404.github.io>.

Single static page. No build step, no framework, no JavaScript — GitHub Pages serves
`index.html` from the repository root directly.

## Layout

```
index.html                  the whole page (inlined CSS)
assets/
  fig-overview.jpg          research setting (from the C³-JEPA manuscript)
  fig-architecture.png      method: slots → control-conditioned predictor → critic
  fig-hardware.jpg          DLROV UVMS system structure
  video-poster.jpg          poster frame for the project video
  salvage-rover-demo.mp4    project walkthrough, 1 min 38 s, 720p
  yuncong-yang-cv.pdf       curriculum vitae
```

## Editing

Everything lives in `index.html`. The figures are downscaled copies of the manuscript
figures; if a figure is updated upstream, re-export it at a long edge of 1400–1640 px
and keep the original aspect ratio (photos as JPEG, diagrams as PNG), then update the
`assets/` file in place.

## Licence

Text and figures © Yuncong Yang. The figures are from a manuscript submitted to IEEE
and are included here for personal academic use.