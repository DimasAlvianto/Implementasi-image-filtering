import numpy as np

# Define the size of the input image and filter
image_width = 5  # Example width of the image
image_height = 5  # Example height of the image
filter_width = 3  # Width of the kernel/filter
filter_height = 3  # Height of the kernel/filter

# Initialize the input image (X), filter/kernel (H), and output image (Y)
X = np.random.rand(image_width, image_height)  # Random values as a sample input image
H = np.array([[1, 0, -1], [1, 0, -1], [1, 0, -1]])  # Example filter for edge detection
Y = np.zeros((image_width - filter_width + 1, image_height - filter_height + 1))

# Convolution operation
for x in range(Y.shape[0]):
    for y in range(Y.shape[1]):
        z = 0
        for k1 in range(filter_width):
            for k2 in range(filter_height):
                z += H[k1, k2] * X[x + k1, y + k2]
        Y[x, y] = z

print("Input Image (X):\n", X)
print("Filter (H):\n", H)
print("Output Image (Y):\n", Y)
