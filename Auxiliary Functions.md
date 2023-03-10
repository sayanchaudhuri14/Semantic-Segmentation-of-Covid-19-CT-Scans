
### revert_img(img):

This Function returns an image of the same size as the original image after performing
some modifications. The images to be passed to this function as arguments are generated
after the Kmeans operation. Consequently, it contains pixel values of 3 quantities. But,
these values are different for every image. To establish uniformity, this function assigns the
values of 0,1,2 to all the pixels. The value to be assigned to every pixel is contingent upon
its frequency of occurrence in the original image.

### KMeans_routine(scan_given):

This function performs Kmeans on the provided CT Scan. Since the original mask has
only 3 values representing background, normal an infected regions, the number of clusters
in the predicted mask is also chosen to be 3. This mask returns the resultant image after
performing the Kmeans on the CT Scan.

### Spec_Sens_acc_f1_INF(mask_given,mask_made): and Spec_Sens_acc_f1_Nor(mask_given,mask_made):

This function is meant to calculate the Dice Score, Accuracy, Sensitivity and Specificity
by comparing the predicted mask from K-Means with expert annotation for both the Normal
and Infected Regions.

### infection(sample):

This function calculates the infection rate of the image passed into it as an argument.
reconstruction_loss(matrix,dimension,flag):
This function takes as input the data matrix and an integer which is the target dimension, after applying PCA on the matrix.This function returns the reconstruction error by taking the MSE between the original matrix and the reconstructed matrix. The additional argument flag specifies if the preserved variance is to be printed.

### f1_val(train,train_label,val,val_label,kernel):

This function fits an SVM classifier on the test set and returns the f1 score of the
predictions of the validation set.

### conv_block(inputs,n_filters,dropout_prob,max_pooling):

Performs Convolutions operation on the provided input twice, applies Max Pooling and
returns the output twice, one to be used for the next layer and the other to be concatenated
with the layer in the upsampling block.

### upsampling_block(expansive_input,contractive_input,n_filters):

Performs Deconvolution operation on the expansive input and concatenates it with the
contractive input. Performs convolution operation twice on the entire layer and returns the
output.

### unet_model(input_size,n_filters,n_classes):

Using the functions mentioned above constructs the model architecture to be used for semantic segmentation.

### get_metrics(scan,mask,class_):

This function takes in an array of scans, masks, and an index number. The above
function returns the average metrics for the scans and masks for the class index passed into
it.

### draw(n):

Displays Original Slice, Expert Mask and the predicted mask and associated metrics for
the index passed.

### perturb(eta):

Tweaks the parameters of the U-Net by the parameter passed into it. Then evaluates
the model performance using the get_metrics function.

### one_slice_uncertainty(scan_idx): Uncertainty(eta,draw,sample_idx):
These two functions work in conjunction to determine the uncertainty of the slice passed
into them.
