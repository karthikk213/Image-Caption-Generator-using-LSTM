# Image-Caption-Generator-using-LSTM

### This project is a sequence-to-sequence model that generates image captions given an image.

### Extracting image features using EfficientNetB4
The code first loads the EfficientNetB4 model from Keras applications, and removes the final classification layer. The model is then used to extract image features from the Flickr30k dataset. The features are saved to a pickle file.

### Cleaning captions text data
Next, the code reads in caption data for the images in the dataset. The captions are preprocessed to lowercase all letters, remove any extra whitespace, and remove any non-alphabetic characters. The captions are also modified to include a "startseq" and "endseq" token to indicate the start and end of the caption.

### Data generator function for training
A data generator is then defined to prepare the data for the model. The generator takes as input the keys (image IDs) for the training or validation set, the caption mapper, the image features, the tokenizer, the maximum caption length, the vocabulary size, and the batch size. The generator generates a batch of data at a time, where each batch consists of the image features, the input sequence (caption up to the current timestep), and the output sequence (next word in the caption).

### Building the model architecture
Finally, the model architecture is defined. The model takes as input the image features and the input sequence, and outputs the next word in the caption. The model is trained using the generator and the Adam optimizer. The loss function is categorical cross-entropy, and the metric is accuracy.

### Compiling and training the model.
The code also includes a plot of the model architecture.

The model is trained for several epochs and achieves an accuracy of around 34%.
