<img width="480" height="311" alt="demo" src="https://github.com/user-attachments/assets/45876337-94f4-4dad-8a2c-3219e01447e7" />
 Context Converter

Convert images, video and audio files straight from the right-click menu.
Select a file, choose **Convert to**, pick a format. The converted file is
saved next to the original, and the original is kept. If a file with the same
name already exists, a number is added, e.g. photo (1).png

 Supported formats
- Images: PNG, JPG/JPEG/JPE/JFIF, WebP, BMP, TIFF, HEIC/HEIF, AVIF, ICO,
  TGA, PSD, SVG, JPEG 2000, JXL, EXR, DDS, RAW photos (CR2, NEF, ARW, DNG, ...)
  and more. Output: JPG, PNG, WebP, AVIF, HEIC, BMP, TIFF, GIF, ICO, TGA, JP2, PDF.
- GIF: to images, or to video (MP4, WebM, MKV, AVI, MOV).
- Video: MP4, MOV, MKV, AVI, WebM, WMV, FLV, MPEG, 3GP, TS, VOB and more.
  Output: another video format, GIF, or an audio format (extracts the audio track).
- Audio: MP3, WAV, FLAC, OGG, Opus, M4A, AAC, WMA, AIFF, AC3, MKA and more.

  Requirements
ffmpeg and ImageMagick must be installed and available in windows powershell:

    winget install Gyan.FFmpeg
    winget install ImageMagick.ImageMagick

Restart Explorer or sign out and back in after installing, so that it picks
up the new PATH.

 Notes
- On Windows 11 the entries are in the classic menu ("Show more options").
- Images are converted with ImageMagick (first frame or page only), video and
  audio with ffmpeg.
- Transparent images converted to JPG or BMP get a white background.
- Support for RAW, HEIC, AVIF and JXL depends on your ImageMagick build.
- Selecting many files starts one conversion per file.

## How it works
The mod does not hook anything. On start it registers the menu entries under
HKCU\Software\Classes (no administrator rights needed) and writes a helper
script to %LOCALAPPDATA%\ContextConverter\convert.ps1. Disabling the mod
removes the menu entries. The script is left in place and can be deleted.
