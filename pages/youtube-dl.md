---
title: youtube-dl
---

## can be used to download videos from webpages with minimal arguments if i go to any directory and run:
### `youtube-dl www.exampleURL.com`
## it will download the YouTube video. plenty of other options available in the man pages
## DOWNLOAD CAPABILITIES
### Single video URL
### Playlist URL (downloads all inidividual vidoes)
### Channel URL (downloads all videos on the entire YouTube channel)
## DOWNLOAD OPTIONS
- `-F` shows all the formats available for the video download
- `-f` followed by a number picks that download options for video quality
- `-f bestaudio` will download only the best audio for the video (GREAT FOR MUSIC DOWNLOADS)
- `-f140` Downloads the highest quality mp4 files with no errors
- `--write-thumbnail` will download the thumbnail(s) of the video(s)
- `--skip-download` will skip the download of the actual video but with other options might do something like still download the thumbnails
## Code

- Formatting filenames of downloaded playlist:
	- ![[#^5850b0]]
- Download just thumbnails
	- ![[#^bcf19b]]
- Download transcripts
	- ![[#^13369b]]
	- Combine with [THIS](https://gist.github.com/glasslion/b2fcad16bc8a9630dbd7a945ab5ebf5e) to clean the output to `.txt`



---
Tags: 

Reference:
<https://ostechnix.com/youtube-dl-tutorial-with-examples-for-beginners/>
Related:


---

```bash
youtube-dl --format mp4 -o "%(upload_date)s %(title)s by %(uploader)s.%(ext)s" <URL>
```

^5850b0

```bash
youtube-dl --write-thumbnail --skip-download <URL>
```

^bcf19b

```bash
youtube-dl --sub-lang en --write-auto-sub --sub-format vtt --skip-download <URL>
```

^13369b
