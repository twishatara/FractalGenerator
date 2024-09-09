# Fractal Tile Renderer

## Overview

This program renders fractal images using multi-threading to divide the work among several threads. It outputs the final result as a `.bmp` image. The fractal rendered is based on the Mandelbrot set, and the image is divided into tiles that are processed concurrently to improve performance.

## Features

- **Fractal Rendering**: The fractal is calculated using the Mandelbrot algorithm and rendered to an image in `.bmp` format.
- **Multi-threading**: The program uses multiple threads to render different parts (tiles) of the image in parallel, reducing the overall render time.
- **Thread-Safe Queue**: A thread-safe queue manages the distribution of work (tiles) to different threads, ensuring efficient task processing without race conditions.

## Points to Note

- The program is designed to render a fractal and output the result as a `.bmp` image.
- Multi-threading ensures that different parts of the image (tiles) are rendered simultaneously, reducing overall render time.
- The program uses the **EasyBMP** library for handling image creation and manipulation.

## How It Works

1. The fractal image is split into smaller tiles.
2. Each tile is assigned to a thread, which computes the fractal for that portion of the image.
3. A thread-safe queue (`ThreadSafeQueue`) is used to manage the tiles and distribute them to the available threads.
4. Once all tiles are processed, the final image is saved as a `.bmp` file.

## Dependencies

- **EasyBMP**: The library used to manage BMP images. Ensure that `EasyBMP.h` is available in your project.

## Usage

1. Clone the repository.
2. Ensure you have the necessary dependencies installed.
3. Build the project using the provided `makefile`.
4. Run the compiled program to generate a fractal image.

## Example

To compile and run the project:

```bash
make
./fractal_tiled
