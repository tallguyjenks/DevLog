

- <https://ostechnix.com/youtube-dl-tutorial-with-examples-for-beginners/>

---

- Can be used to download videos from webpages with minimal arguments if i go to any directory and run:
  - `youtube-dl www.exampleURL.com`
- It will download the YouTube video. plenty of other options available in the man pages
- **DOWNLOAD CAPABILITIES**
  - Single video URL
  - Playlist URL (downloads all individual videos)
  - Channel URL (downloads all videos on the entire YouTube channel)
- **DOWNLOAD OPTIONS**
  - `-F` shows all the formats available for the video download
  - `-f` followed by a number picks that download options for video quality
  - `-f bestaudio` will download only the best audio for the video (GREAT FOR MUSIC DOWNLOADS)
  - `-f140` Downloads the highest quality mp4 files with no errors
  - `--write-thumbnail` will download the thumbnail(s) of the video(s)
  - `--skip-download` will skip the download of the actual video but with other options might do something like still download the thumbnails
