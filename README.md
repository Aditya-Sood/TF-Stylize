# Artistic Style Transfer in Android using TensorFlow

This repository supports the codelab for [Artistic Style Transfer in Android using TensorFlow](https://codelabs.developers.google.com/codelabs/tensorflow-style-transfer-android/). It
is based on code forked from the [TensorFlow](https://github.com/tensorflow/tensorflow) repository.

The model is already trained on a set of classical paintings, and the user is able to choose varying degrees of style from a multiple of those paintings to be transferred to the camera input stream.

Additionally, there's the option to set the resolution of the output stream, and to take a picture of the same which is saved on the device. (The project thus requires permission to access the device Camera and Storage).

This project uses the network proposed by [Dumoulin, et al. 2016](https://arxiv.org/abs/1610.07629) which avoids information duplication when using different networks for different styles, and instead uses a single network trained on multiple styles. As pointed out in the research paper, such a model is capable of "arbitrarily combining the styles learned from individual paintings", which is how the user is able to choose varying degrees of styles from the set of available paintings.

The specific TensorFlow model used in the project is [stylized image transformation model](https://github.com/tensorflow/magenta/blob/master/magenta/models/image_stylization/model.py#L28).

To support the constrained resources environment of mobile devices, the model was optimized using TensorFlow mobile to use smaller data types & remove redundant calculations.