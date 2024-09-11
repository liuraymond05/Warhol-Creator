# Warhol-Creator
Creates a replica of the Marilyn Monroe painting by Andy Warhol out of any image you give.
Inputs: An image containing a clear face that you would like to work with. If there are multiple faces in
the image, the largest one in the frame will be selected.
1. Enter the image of interest into the indicated location in the python script.
2. Enter the BGR colors you would like each of your images in the collage to be based around into
colorsList.
3. The following steps are repeated 9 times on the input image and stored in a list, each one using a
different color from the colors list:
a. First, the cropFace function is applied to the image. This function identifies the largest
face in the frame using Haar-cascade trained data and returns a cropped image containing
only the face.
b. Next, the mapToBlockColors function is applied to the image. This function maps the
function to a color space of only about 64 colors, creating larger blocks of colors.
Morphological transformations are then used to reduce noise and connect blocks of color,
specifically 3 iterations of erosion followed by an iteration of dilation with a kernel size
of 5.
c. Next, the mapColors function is applied to the image to produce the characteristic
popping style of Andy Warhol’s painting. To do this, each block of color is stored in a
dictionary and mapped to another slightly altered, brighter color. To attain the color it is
mapped to, each value in the BGR channel is shifted by a random value before converting
to the HSV color space and scaling up the saturation value, preserving the core color but
brightening the pixels.
4. Finally, the collage function is used to put all images in the list into a 3x3 collage. This uses
indexing techniques to copy over blocks into an array 9 times the size of the original.
Output: A custom artistic image made of a 3x3 grid of edited images, resembling Andy Warhol’s
“Marilyn Monroe.”
