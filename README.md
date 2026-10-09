# Spacefast demos

Small, self-contained demo pages, each published to its own [Spacefast](https://spacefast.com) Space on the **Ryan - DevRel** team. Each folder is one site.

| Folder | Live site | What it is |
|---|---|---|
| [`blocks-7-1/`](blocks-7-1/) | https://will-my-block-break.space.fast/ | Will My Block Break? A WordPress 7.1 block tester. |
| [`wp-kses-tester/`](wp-kses-tester/) | https://wp-kses-tester.space.fast/ | Paste HTML and compare the legacy and new `wp_kses()` parsers, using WordPress nightly in your browser. |

## Deploying

Each Space is connected to this repo with its folder as the root directory, so pushing to `trunk` deploys it.

To publish a folder by hand instead:

```bash
npx -y spacefast publish blocks-7-1
```

Each folder's `.spacefast/space.json` links it to its Space.
