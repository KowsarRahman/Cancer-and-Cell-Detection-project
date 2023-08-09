<strong>Abstract</strong>
<p style="text-align:justify;">Our goal was to explore various deep neural networks for the detection and classification of various cell types in the histopathology images of cancer cells caused due to colon cancer. Our exploration and research included two types of Convolutional Neural Networks (CNN): Very Deep Convolutional Networks (VGG) for Cancer Detection and both Residual Networks (ResNet) and VGG for cell type classification with improvisation and optimization to provide accurate results.
The dataset consisted of 27x27 RGB images of cancer cells from 99 different patients. While inspecting the data, information from patientID 76 was missing so data of 98 patients were used.
Exploratory Data Analysis
The dataset consists of 20280 images that have been classified as cancerous or non cancerous. Out of those, only 9896 images have a label for cell-type named as fibroblast, inflammatory, epithelial, and others, whereas 10384 images do not have a label for cell type.
According to the class distribution output and the column chart displayed in Figure 1(Appendix)
It can be seen that about 4079 of the images are epithelial (41.22%), 2543 as inflammatory (25.77%), 1888 as fibroblast (19.01%) and 1386 belong to the others category (14%).
Figure 2(Appendix) shows the 4 different cell types as digits: (0 for fibroblast, 1 for inflammatory, 2 for epithelial, 3 for others) while Figure 3(Appendix) shows the relationship between the cell types and if they are cancerous or not. We can clearly see from Figure 3 that only epithelial cells are cancerous.</p>

<strong>Task 1</strong>

<p style="text-align:justify;">Using the ‘train_test_split’ function, the dataset is divided into three subsets which are: training, testing and validation. 20 percent of the data would be used for testing while 80 percent of the data is to be used for training. To get a better understanding of the neural networks, we used the Sequential Model API given by TensorFlow.
 
For the baseline model, we used the VGG Model of 3 blocks. The VGG Model may be computationally expensive but it is simpler to implement than other models. It follows an uniform pattern and consists of repeated blocks of convolutional layers, followed by max pooling layers, which makes it easy to understand and implement.
Before working on the final model, we again worked on data augmentation. This time we made some edits to our existing images. We rotated our images to 20 degrees and gave a brightness range from 0.2 to 1.2. In this model, we didn’t use any dropout. The results of this model were so far the best in terms of accuracy. It gave an accuracy of 0.9 which is exactly the same as the original research paper published and also produced a significant decrease in the test loss which recorded 0.26. A lower test loss indicates that the model's predictions are closer to the true labels, indicating better performance. A lower test loss implies that the model has effectively learned the patterns and features in the training data and can generalize well to unseen test data. The final model also had a F1 score of 0.9 too as seen by the learning curve in Figure 6(Appendix). Both the second and third model were saved so that they can be tested independently. Hence, we decided to go with the VGG_Model_3 and carry our prediction using image visualization. As shown in Figure 10(Appendix), any image input from the patch_images directory can be entered into the code and the model will predict if it is cancerous or not.</p>

<strong>Task 2</strong>

<p style="text-align:justify;">Similar to Task 1, the dataset is divided using train_test_split with a 80-20 split. The labels are converted to string format before the ImageDataGenerator is loading the images in batches to memory to be able to compile the baseline model.
Once two baseline models (VGG and ResNet) have been compared, data augmentation has been used with a rotation range of 20, width shift and height shift range of 0.5 and a brightness range of 0.5 to 1.5 for improvised results using increased diversity from such a large dataset of images before using regularization.
</p>
