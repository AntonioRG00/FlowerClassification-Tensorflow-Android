# Image classification w/Android & TensorFlow Lite

This is a fork from [TensorFlow Lite](https://tensorflow.org/lite) for Android. 

It uses image classification to continuously classify whatever it sees from the device's back camera, in this case is about flowers.
Inference is performed using the TensorFlow Lite Java API. 
The app classifies frames in real-time, displaying the top most probable
classifications. It allows the user to select the thread count, and decide whether to run on CPU, GPU, or via [NNAPI](https://developer.android.com/ndk/guides/neuralnetworks).

The model trained and used in this case is with MobileNet (TF Lite Quantized) with [`lib_support`](https://github.com/tensorflow/examples/tree/master/lite/examples/image_classification/android/lib_support) that creates the custom inference pipleline using the
[TensorFlow Lite Support Library](https://www.tensorflow.org/lite/inference_with_metadata/lite_support).

You can also change 'flavorDimensions' (getIsDefault().set(false) to true) to switch between [`lib_support`](https://github.com/tensorflow/examples/tree/master/lite/examples/image_classification/android/lib_support) and [`lib_task_api`](https://github.com/tensorflow/examples/tree/master/lite/examples/image_classification/android/lib_task_api) that leverages the out-of-box API from the
[TensorFlow Lite Task Library](https://www.tensorflow.org/lite/inference_with_metadata/task_library/image_classifier).

## What does classify?

The actual model ([Flower Classification.zip](https://github.com/AntonioRG00/FlowerClassification-Tensorflow-Android/files/7899892/Flower.Classification.zip)) is very poor as it can only classify 5 types of flowers (Poppys, Ivys, Jasmines, Orchids and Roses) you can download it, import the file to https://teachablemachine.withgoogle.com/ and add more examples. To import the new model to Android you just have to replace the files exported from Teachale Machine on assets/converted_tflite_quantized.
