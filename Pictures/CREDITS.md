

The images in this folder come from [Unsplash](https://unsplash.com) and are used under the [Unsplash License](https://unsplash.com/license), which permits free commercial and non-commercial use without permission or attribution. Attribution is appreciated and I like what they're doing with the project, so the credits are recorded here.

| File | Source | Photographer |
| ---- | ------ | ------------ |
| [`photo-1657056852174-4d0e8a3f61ac.jpg`](https://www.google.com/search?q=photo-1657056852174-4d0e8a3f61ac.jpg) | [Unsplash](https://unsplash.com/photos/a-skull-with-a-cross-on-it-9NoJP93rJkI) | [Axel Ruffini](https://unsplash.com/@4xel) |
| [`photo-1768597795859-828bb2b19915.jpg`](https://www.google.com/search?q=photo-1768597795859-828bb2b19915.jpg) | [Unsplash](https://unsplash.com/photos/a-clear-bubble-floats-against-a-dark-background-6YbqLoBXV68) | [Zuzanna Kowalewska](https://unsplash.com/@zuzoi) |
| [`photo-1779089043065-599a0705d0da.jpg`](https://www.google.com/search?q=photo-1779089043065-599a0705d0da.jpg) | [Unsplash](https://unsplash.com/photos/numerous-clear-reflective-spheres-with-blue-and-white-highlights-CiH1lH1u4dc) | [Salvus](https://unsplash.com/@salcrocejpg) |

## Lookup workflow

The steps I usually take are:

1. Query Unsplash for a general concept, make sure to select the free licence from a dropdown.
2. DO NOT CLICK DOWNLOAD
	- Instead, i open the image and delete the question mark and everything behind it (that part carries attributes like resolution downscaling).
3. Download the full-res image and downscale it to fit 3840×2160px with [PowerToys](https://learn.microsoft.com/en-us/windows/powertoys/install?tabs=gh%2Cextract-094) image resizer (or similar).
	- This way of compressing the images ends up much more flattering in the end.

If you swap out or add Unsplash resources of your own, here's how to pull in the credits retroactively:

> [!INFO] Filenames
> The filenames filenames (photo-< timestamp >-< hash >.jpg) are Imgix CDN asset hashes.
> Unsplash's public API does not index CDN hashes directly, but Google does.

```bash
# 1. Open Google search for the filename to find the Unsplash photo page:

# Windows (PowerShell):
      Start-Process "https://www.google.com/search?q=<filename>"

# macOS:
      open "https://www.google.com/search?q=<filename>"

# Linux:
      xdg-open "https://www.google.com/search?q=<filename>"

# 2. Extract the photo slug/ID from the Unsplash URL (e.g. unsplash.com/photos/<id>) and fetch the attribution metadata:
      curl -s "https://unsplash.com/napi/photos/<id>" | jq '{
        photographer: .user.name,
        username:     .user.username,
        profile:      .user.links.html,
        photo:        .links.html
      }'
```
