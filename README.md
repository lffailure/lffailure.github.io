# Learning from Failure: Training on Failed Rollouts with Stitched Expert Recovery for Articulated Object Opening

Project page for an anonymous ICRA 2027 submission: https://lffailure.github.io/

## Media files

Put these files in place. `index.html` already points to them.

| Path | Content |
|---|---|
| `static/videos/teaser.mp4` | Teaser shown under the title |
| `static/images/method_overview.png` | Pipeline figure |
| `static/videos/sim_1.mp4` … `sim_3.mp4` | Simulation rollouts |
| `static/videos/baseline_fail.mp4`, `ours_recover.mp4` | Side-by-side failure case |
| `static/videos/real_1.mp4`, `real_2.mp4` | Real-robot rollouts |
| `static/videos/supplementary.mp4` | Full supplementary video |

Compress videos before committing; GitHub rejects files over 100 MB:

```bash
ffmpeg -i in.mp4 -vcodec libx264 -crf 28 -preset slow -an -map_metadata -1 out.mp4
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
