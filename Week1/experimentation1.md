# Task 1
# Objective
To create an edge detection algorithm
# Steps taken
First input image is read by matplotlib
Then converted image to grayscale using weighted average method that I found after researching. The blog link is: https://samirkhanal35.medium.com/grayscale-conversion-56189cd0e9ca
Made a convolution function which takes input matrix, kernel and padding width as arguments
Applied convolution of grayscale image with Sobel matrix plotted result
Applied convolution of grayscale image with Laplace matrix, plotted result
Observed Laplace operator gives better edge detection

# Explaining Observations
Sobel matrix works on first order derivative between intensity values of the image. The region of constant intensity becomes zero and edges gives a peak in first order derivative graph. But, this is not a good tool to determine edges at different angles as we can see from our algorithm, horizontal and vertical edges are detected but other edges are not detected.

Laplacian works on second derivative of intensity. Here, graph of laplacian gives zero in edges. We can detect edges by detecting zero crossings (these are sharp crossings between positive to negative around zero points). This is done by setting a threshold value which depends on input image. Upon experimenting with threshold value, too high threshold value fails to detect edges and too little threshold value detects unnecessary edges. Overall, laplacian method seems more effective to detect edges. Before using laplacian it is better to use gaussian blur as the second derivative is more sensitive to noise in the image and gauss filter reduces noise from the image.
