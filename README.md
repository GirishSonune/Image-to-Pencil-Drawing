# Pencil Sketch Generator

This project demonstrates how to transform an image into a pencil sketch using Python and OpenCV. The code processes an input image to create a visually appealing sketch effect by combining various image manipulation techniques.

## Features
- Convert any image to a grayscale representation.
- Apply Gaussian blur and inversion to create a pencil sketch effect.
- Save the output sketch as an image file.

## Technologies Used
- Python
- OpenCV (cv2)

## Prerequisites
Ensure you have Python installed along with OpenCV. You can install OpenCV using pip:

```bash
pip install opencv-python
```

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/GirishSonune/Image-to-Pencil-Drawing.git
   cd Image-to-Pencil-Drawing
   ```

2. Add your image to the project directory. Replace `ViratKohli.jpg` in the code with the path to your image file.

3. Run the notebook or script to generate the sketch.

## Code Overview

1. **Import OpenCV:**
   ```python
   import cv2
   ```

2. **Read and Process the Image:**
   ```python
   image = cv2.imread("ViratKohli.jpg")
   gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
   inverted = 255 - gray_image
   blur = cv2.GaussianBlur(inverted, (21, 21), 0)
   inverted_blur = 255 - blur
   sketch = cv2.divide(gray_image, inverted_blur, scale=250.0) # Adjust scale as needed
   ```

3. **Save the Output:**
   ```python
   cv2.imwrite("sketch_image.png", sketch)
   ```

## Usage
- Run the code in a Jupyter Notebook or Python script.
- Provide the path to your input image.
- The sketch image will be saved as `sketch_image.png` in the same directory.

## Example
Input Image:
![Input Image](example_input.jpg)

Output Sketch:
![Sketch Image](example_sketch.png)

## Contributing
Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature-name`.
3. Commit your changes: `git commit -m 'Add feature-name'`.
4. Push to the branch: `git push origin feature-name`.
5. Open a pull request.

## License
This project is licensed under the MIT License. See the LICENSE file for more details.

---

Enjoy creating stunning pencil sketches!
