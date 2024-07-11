### #Steganography - Hiding an Image Inside Another
#### Description:
This Python script allows you to hide one image inside another using steganography techniques. It provides functionality to merge two images, hiding one within the other, and to extract a hidden image from a merged image.

##### Requirements:
Python 3.x
Pillow library for image processing
You can install the required library using pip:

bash
Copy code
pip install pillow


#### Usage:
The script supports two main commands: merge to hide an image inside another, and unmerge to extract the hidden image.

Merge Command
To hide an image (image2) inside another image (image1), use the following command:

bash
Copy code
python steganography.py merge --image1 <path_to_image1> --image2 <path_to_image2> --output <output_path>
Unmerge Command
To extract the hidden image from a merged image, use the following command:

bash
Copy code
python steganography.py unmerge --image <path_to_image> --output <output_path>
Example
To hide secret.png inside cover.png and save the result as merged.png:

bash
Copy code
python steganography.py merge --image1 cover.png --image2 secret.png --output merged.png
To extract the hidden image from merged.png and save it as extracted.png:

bash
Copy code
python steganography.py unmerge --image merged.png --output extracted.png
#### Code Description:
# Steganography Class:
The Steganography class provides methods for hiding an image inside another and extracting it.

# Constants

# BLACK_PIXEL: A constant representing a black pixel (0, 0, 0).
Methods

_int_to_bin(self, rgb): Converts an RGB tuple of integers to a tuple of binary strings.

# Parameters: rgb - An integer tuple like (220, 110, 96).
Returns: A tuple of binary strings like ("11011100", "01101110", "01100000").
_bin_to_int(self, rgb): Converts a tuple of binary strings to an RGB tuple of integers.

# Parameters: rgb - A string tuple like ("11011100", "01101110", "01100000").
Returns: An integer tuple like (220, 110, 96).
_merge_rgb(self, rgb1, rgb2): Merges two RGB tuples.

# Parameters:
rgb1: An integer tuple like (220, 110, 96).
rgb2: An integer tuple like (240, 95, 105).
Returns: An integer tuple with the two RGB values merged.
_unmerge_rgb(self, rgb): Extracts the hidden RGB values from a merged RGB tuple.

# Parameters: rgb - An integer tuple like (220, 110, 96).
Returns: An integer tuple with the hidden RGB values.
merge(self, image1, image2): Merges image2 into image1.

# Parameters:
image1: The cover image.
image2: The image to hide inside image1.
Returns: A new merged image.
unmerge(self, image): Extracts the hidden image from a merged image.

# Parameters: image - The merged image.
Returns: The extracted hidden image.
Main Function
The main function handles the command-line interface for the script.

# Commands:
# merge: Merges two images.
Arguments:
--image1: Path to the first image (cover image).
--image2: Path to the second image (hidden image).
--output: Path to save the merged output image.
# unmerge: Extracts a hidden image.
Arguments:
--image: Path to the merged image.
--output: Path to save the extracted hidden image.
