# Description:
# Scripts used to generate TensorFlow Python API.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

py_binary(
    name = "create_python_api",
    srcs = ["create_python_api.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python",
    ],
)

py_test(
    name = "create_python_api_test",
    srcs = ["create_python_api_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":create_python_api",
        "//tensorflow/python:client_testlib",
    ],
)

genrule(
    name = "python_api_gen",
    # List of API files. This list should include file name for
    # every module exported using tf_export. For e.g. if an op is decorated with
    # @tf_export('module1.module2', 'module3'). Then, outs should include
    # api/module1/module2/__init__.py and api/module3/__init__.py.
    # keep sorted
    outs = [
        "api/__init__.py",
        "api/app/__init__.py",
        "api/bitwise/__init__.py",
        "api/compat/__init__.py",
        "api/contrib/__init__.py",
        "api/contrib/stat_summarizer/__init__.py",
        "api/data/__init__.py",
        "api/distributions/__init__.py",
        "api/distributions/bijectors/__init__.py",
        "api/errors/__init__.py",
        "api/estimator/__init__.py",
        "api/estimator/export/__init__.py",
        "api/estimator/inputs/__init__.py",
        "api/feature_column/__init__.py",
        "api/gfile/__init__.py",
        "api/graph_util/__init__.py",
        "api/image/__init__.py",
        "api/initializers/__init__.py",
        "api/keras/__init__.py",
        "api/keras/activations/__init__.py",
        "api/keras/applications/__init__.py",
        "api/keras/applications/densenet/__init__.py",
        "api/keras/applications/inception_resnet_v2/__init__.py",
        "api/keras/applications/inception_v3/__init__.py",
        "api/keras/applications/mobilenet/__init__.py",
        "api/keras/applications/nasnet/__init__.py",
        "api/keras/applications/resnet50/__init__.py",
        "api/keras/applications/vgg16/__init__.py",
        "api/keras/applications/vgg19/__init__.py",
        "api/keras/applications/xception/__init__.py",
        "api/keras/backend/__init__.py",
        "api/keras/callbacks/__init__.py",
        "api/keras/constraints/__init__.py",
        "api/keras/datasets/__init__.py",
        "api/keras/datasets/boston_housing/__init__.py",
        "api/keras/datasets/cifar10/__init__.py",
        "api/keras/datasets/cifar100/__init__.py",
        "api/keras/datasets/fashion_mnist/__init__.py",
        "api/keras/datasets/imdb/__init__.py",
        "api/keras/datasets/mnist/__init__.py",
        "api/keras/datasets/reuters/__init__.py",
        "api/keras/estimator/__init__.py",
        "api/keras/initializers/__init__.py",
        "api/keras/layers/__init__.py",
        "api/keras/losses/__init__.py",
        "api/keras/metrics/__init__.py",
        "api/keras/models/__init__.py",
        "api/keras/optimizers/__init__.py",
        "api/keras/preprocessing/__init__.py",
        "api/keras/preprocessing/image/__init__.py",
        "api/keras/preprocessing/sequence/__init__.py",
        "api/keras/preprocessing/text/__init__.py",
        "api/keras/regularizers/__init__.py",
        "api/keras/utils/__init__.py",
        "api/keras/wrappers/__init__.py",
        "api/keras/wrappers/scikit_learn/__init__.py",
        "api/layers/__init__.py",
        "api/linalg/__init__.py",
        "api/logging/__init__.py",
        "api/losses/__init__.py",
        "api/manip/__init__.py",
        "api/metrics/__init__.py",
        "api/nn/__init__.py",
        "api/nn/rnn_cell/__init__.py",
        "api/profiler/__init__.py",
        "api/python_io/__init__.py",
        "api/resource_loader/__init__.py",
        "api/saved_model/__init__.py",
        "api/saved_model/builder/__init__.py",
        "api/saved_model/constants/__init__.py",
        "api/saved_model/loader/__init__.py",
        "api/saved_model/main_op/__init__.py",
        "api/saved_model/signature_constants/__init__.py",
        "api/saved_model/signature_def_utils/__init__.py",
        "api/saved_model/tag_constants/__init__.py",
        "api/saved_model/utils/__init__.py",
        "api/sets/__init__.py",
        "api/spectral/__init__.py",
        "api/summary/__init__.py",
        "api/sysconfig/__init__.py",
        "api/test/__init__.py",
        "api/train/__init__.py",
        "api/train/queue_runner/__init__.py",
        "api/user_ops/__init__.py",
    ],
    cmd = "$(location create_python_api) $(OUTS)",
    tools = ["create_python_api"],
)

py_library(
    name = "python_api",
    srcs = [":python_api_gen"],
    srcs_version = "PY2AND3",
    visibility = ["//tensorflow:__subpackages__"],
    deps = [
        "//tensorflow/contrib:contrib_py",  # keep
        "//tensorflow/python",  # keep
    ],
)
