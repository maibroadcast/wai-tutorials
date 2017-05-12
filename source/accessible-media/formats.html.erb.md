---
title: Caption formats and examples
order: 3
status: editors-draft
wcag_success_criteria:
  - 1.2.2
editors:
  - Geoff Freed
contributors:
  - The Education and Outreach Working Group (<a href="https://www.w3.org/WAI/EO/">EOWG</a>)
support: Developed with support from the <a href="https://www.w3.org/WAI/@@/">@@ project</a>
---
## Caption formats

Nearly all modern user agents (browsers, media players) on both desktop
and mobile platforms provide support for the display of closed captions,
but not all support the same caption-delivery formats. The two most
common formats used for online media are listed below.

-   [Timed Text Markup Language
    (TTML)](https://www.w3.org/TR/ttaf1-dfxp/)
-   [Web Video Text Tracks (WebVTT)](https://w3c.github.io/webvtt/)
-   [SRT](https://matroska.org/technical/specs/subtitles/srt.html)

The table below shows which formats are supported by which browsers.


<table>
	<tr>
		<th scope="col">Browser</th>
		<th scope="col">OS</th>
		<th scope="col">Supported caption format(s)</th>
	</tr>
	<tr>
		<th scope="row">Firefox</th>
		<td>Windows, OS X, Android, iOS</td>
		<td>WebVTT</td>
	</tr>
	<tr>
		<th scope="row">IE 10, 11; Edge</th>
		<td>Windows</td>
		<td>TTML, WebVTT</td>
	</tr>
	<tr>
		<th scope="row">Safari</th>
		<td>OS X; iOS</td>
		<td>WebVTT</td>
	</tr>
	<tr>
		<th scope="row">Chrome</th>
		<td>Windows, OS X, Chrome OS, Android, iOS</td>
		<td>WebVTT</td>
	</tr>
</table>

SRT is not supported natively by any browser, but is supported by most
other types of media players including those provided by popular
video-hosting services, some social-media platforms and by custom
players.

WebVTT, TTML and SRT are "sidecar" files, which is to say they are
transmitted separately from their corresponding video files (riding
alongside the video data in the delivery stream, rather than being
embedded directly into the video file), and are synchronized and
displayed by the user agent at the time of playback.

## Delivering captions to viewers

Captions are delivered to viewers using HTML5's `track` element, which
was created specifically for carrying text tracks, such as captions,
subtitles and [text-based audio descriptions](g). `track` is used as a
child element of the `video` element:

Code snippet:

~~~html
<video controls>
    <source src="myvideo.mp4" type="video/mp4" />
        <track kind="captions" src="myvideo_captions.vtt" srclang="en" label="Captions" default />
</video>
~~~