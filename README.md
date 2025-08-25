# SV-document-scanner
# Document Scanner with OpenCV
- An automatic document scanner built with Python and OpenCV that detects, outlines, and prepares a document from an image for further processing.
# Features
- Automatic Edge Detection: Automatically finds the edges of a document, even on cluttered backgrounds.
- Perspective Transformation: Applies a perspective transform to achieve a top-down view of the document.
- Resizing and Pre-processing: Resizes and pre-processes the image with grayscale, blurring, and Canny edge detection to improve contour finding.
- Error Handling: Provides clear messages if a document's contour cannot be found.
# Requirements
This project uses several standard Python libraries. You can install them using pip:
```sh
pip install numpy opencv-python imutils scikit-image
```

How to Use
Clone the repository:
```sh
git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name
```


Ensure you have an image file ready to be scanned, for example, example-image.jpg.
Run the script from the terminal, providing the image path with the -i or --image argument:

### How to Run

To run the script, open your terminal or command prompt, go to the project directory, and use the following command. Replace `example-image.jpg` with your image file's path.

```sh
python scan.py -i example-image.jpg
```


The script displays the processed image with the document's outline. Press any key while the image windows are active to continue.


Ensure the document is clearly distinguishable from its background.

Use a higher-quality image with good contrast.

The script is designed to handle this gracefully and will print No four-sided contour (document) was found instead of crashing.

## Code Explanation

The argparse module handles command-line arguments to accept the input image file.

`cv2.imread()` loads the image from the specified file path.

The image is resized and pre-processed with grayscale, Gaussian blur, and Canny edge detection.

`cv2.findContours()` is used to find the outlines of objects in the image.

The contours are sorted to find the largest ones, and the script loops through them to find the first one with four points, assuming this is the document.

If a four-sided contour (screenCnt) is found, `cv2.drawContours()` draws a green outline around it.

Contributing

You are welcome to open an issue or submit a pull request if you have suggestions for improvements.

 -savjeet singh
