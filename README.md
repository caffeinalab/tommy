# Tommy: Web Assets converter and optimizer

Tommy will process and optimize all your static assets ready for the web no matter what is the file extensions.

It will cache yet processed files so that future executions will be fast.

You can optionally configure Tommy to upload all your processed assets to a S3 bucket.

### Handled files

- `jpg, jpeg` will be converted with `imagemagick` and optimized with `jpegoptim`
- `png` will be converted with `imagemagick` and optimized with `pngquant`
- `gif` will be optimized with `gifsicle`
- `svg` will be optimized with `svgo`

- _JPG/PNG files_ will be resized and optimized in multiple images
- _video files_ will be converted to `mp4, webm` using `ffmpeg` and a poster will be extracted

- _All other static assets_ will be just copied and remain untouched.

## How to: run with Docker

```
docker run \
-v "${ABSPATH_TO_SRC_DIRECTORY}":/src \
-v "${ABSPATH_TO_DEST_DIRECTORY}":/dst \
kopiro/tommy
```

Please note that:

- `${ABSPATH_TO_SRC_DIRECTORY}` is the path of your original assets.
- `${ABSPATH_TO_DEST_DIRECTORY}` is the path where you want processed files.

## How to: run in MacOS

You've to install upfront all converters. With `brew` installed, you could run `./macos.sh`,
then: `cd app && npm i`.

To run Tommy:

```
SRC_DIR=${ABSPATH_TO_SRC_DIRECTORY} DST_DIR=${ABSPATH_TO_DEST_DIRECTORY} node ./app/index.js
```

## License

MIT
