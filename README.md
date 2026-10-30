# Image-Handling-and-Pixel-Transformations-Using-OpenCV

## Aim:

Write a Python program using OpenCV that performs the following tasks:

Read and Display an Image.
Adjust the brightness of an image.
Modify the image contrast.
Generate a third image using bitwise operations.

## Software Required:
Anaconda - Python 3.7

Jupyter Notebook (for interactive development and execution)

## Algorithm:

Step 1:
Load an image from your local directory and display it.

Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image. Display the original, brighter, and darker images.

Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2.

Step 5:
Split the image into B, G, R components and display the channels.

## Program:

```python
Developed by: Naveenkumar M
Reg.No: 212224230182

import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('ME.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
# Load the image
image = cv2.imread('ME.jpg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('ME.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(400,300),150,(255,0,0),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('ME.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('ME.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, "Naveen", (50, 150), cv2.FONT_HERSHEY_SIMPLEX, 3, (0, 0, 0), 5)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)

plt.imshow(text_img, cmap='viridis')  
plt.title("212224230182")
plt.axis('on')  
plt.show()

# Load the image
image = cv2.imread('ME.jpg')

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)

# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")

# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")

# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)

plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")

# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[200:500, 200:500] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499

# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('ME.jpg')

image.shape
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape

# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('ME.jpg')
image.shape

# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()

# Load the image
image = cv2.imread('ME.jpg')
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)

# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")

# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")

```

## Output:

### Original image
<img width="297" height="410" alt="734c003b-d0f9-4fc9-ba47-742ae3366496" src="https://github.com/user-attachments/assets/c03c21fd-0998-4da3-9e98-a1a1307c222d" />

### Image with line
<img width="297" height="410" alt="8c3a8102-9d9d-400c-9227-bea8e71200d9" src="https://github.com/user-attachments/assets/8e893c41-c64e-4f94-a1f8-1bf26fd0e7fb" />

### Image with circle
<img width="297" height="410" alt="e368d1e1-a36b-4310-b341-a56c7cd7b971" src="https://github.com/user-attachments/assets/38fe14b5-6b28-4d15-a1e4-6dbc894e179a" />

### Image with rectangle
<img width="297" height="410" alt="56fbcc50-8d30-4f81-bb91-9b4cf5cd63ab" src="https://github.com/user-attachments/assets/394b8638-6b3c-4b72-8991-d576c52a802e" />

### Image with opencv drawing
<img width="342" height="434" alt="748e2534-e4b7-4613-bb33-f2d823ee31f0" src="https://github.com/user-attachments/assets/0588de56-b609-4832-acc8-1afcdec47590" />

### Image with RGB
<img width="297" height="410" alt="2924c056-97d5-4789-91a5-9ecfe7baa9da" src="https://github.com/user-attachments/assets/8090bf05-5826-4f44-bb6b-73bf341c7189" />

### HSV image
<img width="297" height="410" alt="8ddb3c17-9a57-49fe-97b1-479a3e02f3d0" src="https://github.com/user-attachments/assets/d3bb62f3-9783-439f-8e75-f0e72fb752af" />

### Grayscale image
<img width="297" height="410" alt="e6bfdf45-fdfb-407c-a61d-0dd0f2da545f" src="https://github.com/user-attachments/assets/7d3b7b7b-fc32-48b8-921a-38e9bc66ed81" />

### YCrCb image
<img width="297" height="410" alt="ad2f5204-6ccb-462e-b66a-daaa7baaa290" src="https://github.com/user-attachments/assets/94284ce5-6bc1-4cb7-9c6e-975a7e0d734a" />

### HSV to RGB image
<img width="297" height="410" alt="dcb59a6e-d264-4249-b4b9-e59f1f1714f1" src="https://github.com/user-attachments/assets/89978c50-d862-41b5-a41e-4becbd43ab57" />

### Image with 300x300 white block
<img width="302" height="410" alt="4808f1d1-933d-4ec7-bc49-d681cb0a9f9b" src="https://github.com/user-attachments/assets/e86d4c57-3545-4bd9-93dc-9e7db79f0ae3" />

### Image with resized
<img width="493" height="410" alt="3d99f038-1a21-4291-a888-a2d8d174425a" src="https://github.com/user-attachments/assets/2b2a1a9b-3b5e-4c35-b083-9a15c96a6826" />

### Image with Crop
<img width="389" height="410" alt="0caebdf3-7fc7-4b25-bcf8-ef7c48406cfe" src="https://github.com/user-attachments/assets/51662b4d-9e9b-4c17-838e-e42821f8b676" />

### Flipped horizontally
<img width="297" height="410" alt="08249a84-8fe3-487b-83d0-f6f7fd2047f1" src="https://github.com/user-attachments/assets/54bf28a3-fb13-4177-88a4-46b4cb0d3d20" />

### Flipped vertically
<img width="297" height="410" alt="33363efd-ab6d-4776-935b-e3969a4842a6" src="https://github.com/user-attachments/assets/8fa57596-8b96-4e65-88d3-80870b771f7a" />


## Result:
Thus, the Image-Handling-and-Pixel-Transformations-Using-OpenCV project is completed successfuly.
