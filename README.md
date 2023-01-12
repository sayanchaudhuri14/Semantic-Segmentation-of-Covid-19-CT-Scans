# Semantic-Segmentation-of-Covid-19-CT-Scans


Dataset: The dataset consists of 3554 CT scans of Covid-19 infected patients and their corresponding expert annotated masks for Normal and Infected Regions.
Link : https://drive.google.com/drive/folders/1OD6hNnD0l-klFcl3ZLkgEaZoUz4fPtrB?usp=sharing

Introduction:

•	First of all, I investigated the dataset distribution using the expert annotation and categorized them into Normal, Mild, and Severe cases. 

•	I start off by analysing the the performance of KMeans on provided CT Scans and comparing the predicted masks with the expert annotations based on the averaged dice score, sensitivity, specificity, and accuracy. 

•	Thereafter, I reconstructed the given CT Scans from limited angle sinograms at 4x and 8x resolutions and found the averaged quality metrics PSNR and SSIM for them. Applied the KMeans on the reconstructed images again and sought the averaged dice score, sensitivity, specificity, and accuracy. 

•	Additionally, displayed apposite samples to mark the progress of the project. 

•	After analysing the performance of KMeans, I implemented the PCA algorithm.

•	I performed PCA on a given data and projected the high dimensional CT embeddings to 100 and 50 dimensions. Plotted a graph between the reconstruction error and the number of principal components.

•	In the next part, I applied PCA to covid-19 mask dataset, and further, it was split into train-test-val sets. I applied with linear and RBF kernels to classify the embeddings into Normal, Mild, and Severe categories. Finally, I reported the Accuracy and F1-scored for the training and test datasets for all the classes.

•	Then, I trained a U-Net model using the given dataset after applying
felicitous augmentations and pre-processing. Following which, I reconstructed the CT scans using limited-angle sinograms and predicted the segmentation masks of the reconstructed test cases.

•	Finally, to ensure robustness of my model, tweaked the model parameters and computed the metrics for various cases. Drew the uncertainty plots for sample slices to correlate them with the errors observed.

•	I reported the Accuracy, F1 score, Specificity and Sensitivity for all the cases.

•	For seamless implementation, scripted a few auxiliary functions which I have described in a separate file.
