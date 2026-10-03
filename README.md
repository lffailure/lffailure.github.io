# Learning from Failure: Training on Failed Rollouts with Stitched Expert Recovery for Articulated Object Opening

Project page for an anonymous ICRA 2027 submission: https://lffailure.github.io/

## Media files

Drop files at these paths; `index.html` already points to them. A slot whose file is missing is hidden automatically, so the page can go live before every file exists.

```
static/
├── images/
│   ├── teaser.png             Fig. 1  (under the title)
│   ├── pipeline.png           Fig. 2  (Method)
│   ├── fr_examples.png        Fig. 4  (Generated Failure-Recovery Data)
│   ├── table_per_object.png   Table I (Results, with object thumbnails)
│   └── qualitative.png        Fig. 5  (Qualitative Comparison)
└── videos/
    ├── fr/                    stitched FR trajectories, one per failure type
    │   ├── fr_miss_handle.mp4
    │   ├── fr_push_closed.mp4
    │   ├── fr_lose_contact.mp4
    │   └── fr_collision.mp4
    ├── comparison/            same initial state, baseline vs. ours
    │   ├── grasp_baseline.mp4
    │   ├── grasp_ours.mp4
    │   ├── collision_baseline.mp4
    │   └── collision_ours.mp4
    └── supplementary.mp4      full video
```

Images: PNG, about 2000 px wide. Export figures from the source files rather than screenshotting the PDF.

Videos: H.264 MP4, no audio, metadata stripped. GitHub rejects files over 100 MB; keep clips under ~10 MB:

```bash
ffmpeg -i in.mp4 -vcodec libx264 -crf 28 -preset slow -pix_fmt yuv420p -vf "scale=1280:-2" -an -map_metadata -1 -movflags +faststart out.mp4
```

## Double-blind checklist (until the decision)

- No author names, affiliations, lab links, or social handles anywhere, including HTML comments
- Strip metadata from media: `exiftool -all= -overwrite_original static/**/*`
- Check video frames for lab signage, logos, faces, or recognizable rooms
- Host videos here, not on a personal YouTube channel
- No analytics or trackers (they can expose reviewers)
- Use an anonymized code mirror (e.g. anonymous.4open.science), not a personal repo
- Commit with an anonymous git identity (see below)
- Keep `<meta name="robots" content="noindex, nofollow">`

```bash
git config user.name  "lffailure"
git config user.email "329662581+lffailure@users.noreply.github.com"
```

## Credits

Built on the [Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template), adapted from [Nerfies](https://nerfies.github.io).
