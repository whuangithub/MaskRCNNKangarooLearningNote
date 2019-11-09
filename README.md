This is one examplt using Mask RCNN with kangaroo dataset.
I hope this could be one example in "real world setting", although the dataset is not large enough.

The tutorial:https://machinelearningmastery.com/how-to-train-an-object-detection-model-with-keras/

I run this project on the Docker image tensorflow/tensorflow:1.15.0-gpu-py3 with several package installed.

The main problem I met is:

    # Error : Failed to get convolution algorithm. This is probably because cuDNN failed to initialize, so try looking to see if a warning log message was printed above.
    # https://github.com/tensorflow/tensorflow/issues/24828
    # Suggests the following solution

    from tensorflow.compat.v1 import ConfigProto
    from tensorflow.compat.v1 import InteractiveSession

    config0 = ConfigProto()
    config0.gpu_options.allow_growth = True
    session = InteractiveSession(config=config0)

Someone suggested that the problem could be solve in tensorflow 1.8.0, but the version is too old to run this project.

I will try to apply the Mask RCNN on a larger dataset.
