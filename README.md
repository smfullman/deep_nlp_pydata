# PyData NLP Presentation

This repo has the code for the PyData Chicago talk on Deep NLP.  The full presentation can be found here: https://slides.com/smfullman/making-sense-of-text-data-with-deep-nlp/

### Notebooks

* 00_warmup_example: a quick example using Keras to build a multi-class classifier model
* 01_establish_a_baseline: Create a linear model for IMDB sentiment classification
* 02a_just_word_vectors: Create a model using word vectors for IMDB sentiment classification
* 02b_just_word_vectors_and_conv_layers: Same as 2a but with convoutional layers, and visualizations
* 03_imdb_model: Create a model for IMDB sentiment classification using Embeddings, Conv, LSTM, and Attention
* 04_language_model_data_processing: Heavy lifting for langauge model data prep
* 05_language_model_training_and_transfer_learning: Create a language model using Amazon review data and transfer the weights to an IMDB sentiment classification model


### Dockerfile

A dockerfile that can be used to create an image which runs all notebooks.  Uses GPU implementations of tensorflow and keras.  Requires nvidia-docker: https://github.com/nvidia/nvidia-docker/wiki/Installation-(version-2.0)

To build:
<pre>
docker build -t image_name .
</pre>

To run:
<pre>
NV_GPU=1 nvidia-docker run -it -p 9999:9999 -v /your/notebook/folder:/home image_name /bin/bash -c "/opt/conda/bin/jupyter notebook --notebook-dir=/home --ip=* --port=9999 --no-browser --allow-root"
</pre>