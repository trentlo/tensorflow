load("//tensorflow/lite:build_def.bzl", "tflite_copts")
load(
    "//tensorflow/lite/experimental/micro/testing:micro_test.bzl",
    "tflite_micro_cc_test",
)

package(
    default_visibility = [
        "//visibility:public",
    ],
    licenses = ["notice"],  # Apache 2.0
)

cc_library(
    name = "micro_ops",
    srcs = [
        "arg_min_max.cc",
        "ceil.cc",
        "comparisons.cc",
        "conv.cc",
        "depthwise_conv.cc",
        "elementwise.cc",
        "floor.cc",
        "fully_connected.cc",
        "logical.cc",
        "maximum_minimum.cc",
        "pack.cc",
        "pooling.cc",
        "prelu.cc",
        "reshape.cc",
        "round.cc",
        "softmax.cc",
        "split.cc",
        "strided_slice.cc",
        "unpack.cc",
    ],
    hdrs = [
    ],
    copts = tflite_copts(),
    deps = [
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro/kernels:micro_utils",
        "//tensorflow/lite/kernels:kernel_util",
        "//tensorflow/lite/kernels:op_macros",
        "//tensorflow/lite/kernels:padding",
        "//tensorflow/lite/kernels/internal:common",
        "//tensorflow/lite/kernels/internal:quantization_util",
        "//tensorflow/lite/kernels/internal:reference_base",
        "//tensorflow/lite/kernels/internal:strided_slice_logic",
        "//tensorflow/lite/kernels/internal:tensor",
    ],
)

cc_library(
    name = "all_ops_resolver",
    srcs = [
        "all_ops_resolver.cc",
    ],
    hdrs = [
        "all_ops_resolver.h",
    ],
    copts = tflite_copts(),
    deps = [
        ":micro_ops",
        "//tensorflow/lite/experimental/micro:micro_framework",
    ],
)

cc_library(
    name = "portable_optimized_micro_ops",
    srcs = [
        "arg_min_max.cc",
        "ceil.cc",
        "comparisons.cc",
        "conv.cc",
        "elementwise.cc",
        "floor.cc",
        "fully_connected.cc",
        "logical.cc",
        "maximum_minimum.cc",
        "pack.cc",
        "pooling.cc",
        "portable_optimized/depthwise_conv.cc",
        "prelu.cc",
        "reshape.cc",
        "round.cc",
        "softmax.cc",
        "split.cc",
        "strided_slice.cc",
        "unpack.cc",
    ],
    hdrs = [
    ],
    copts = tflite_copts(),
    deps = [
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro/kernels:micro_utils",
        "//tensorflow/lite/kernels:kernel_util",
        "//tensorflow/lite/kernels:op_macros",
        "//tensorflow/lite/kernels:padding",
        "//tensorflow/lite/kernels/internal:common",
        "//tensorflow/lite/kernels/internal:quantization_util",
        "//tensorflow/lite/kernels/internal:reference_base",
        "//tensorflow/lite/kernels/internal:strided_slice_logic",
        "//tensorflow/lite/kernels/internal:tensor",
    ],
)

cc_library(
    name = "portable_optimized_ops_resolver",
    srcs = [
        "all_ops_resolver.cc",
    ],
    hdrs = [
        "all_ops_resolver.h",
    ],
    copts = tflite_copts(),
    deps = [
        ":portable_optimized_micro_ops",
        "//tensorflow/lite/experimental/micro:micro_framework",
    ],
)

tflite_micro_cc_test(
    name = "elementwise_test",
    srcs = ["elementwise_test.cc"],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "pooling_test",
    srcs = [
        "pooling_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "depthwise_conv_test",
    srcs = [
        "depthwise_conv_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "portable_optimized_depthwise_conv_test",
    srcs = [
        "depthwise_conv_test.cc",
    ],
    deps = [
        ":portable_optimized_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "fully_connected_test",
    srcs = [
        "fully_connected_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "softmax_test",
    srcs = [
        "softmax_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "conv_test",
    srcs = [
        "conv_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "prelu_test",
    srcs = [
        "prelu_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "floor_test",
    srcs = [
        "floor_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "logical_test",
    srcs = [
        "logical_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "maximum_minimum_test",
    srcs = [
        "maximum_minimum_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "arg_min_max_test",
    srcs = [
        "arg_min_max_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/kernels:micro_utils",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "comparisons_test",
    srcs = [
        "comparisons_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/kernels:micro_utils",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "ceil_test",
    srcs = [
        "ceil_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "round_test",
    srcs = [
        "round_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "strided_slice_test",
    srcs = [
        "strided_slice_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "pack_test",
    srcs = [
        "pack_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "unpack_test",
    srcs = [
        "unpack_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

tflite_micro_cc_test(
    name = "split_test",
    srcs = [
        "split_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)

cc_library(
    name = "micro_utils",
    hdrs = ["micro_utils.h"],
)

tflite_micro_cc_test(
    name = "reshape_test",
    srcs = [
        "reshape_test.cc",
    ],
    deps = [
        ":all_ops_resolver",
        "//tensorflow/lite/c:c_api_internal",
        "//tensorflow/lite/experimental/micro:micro_framework",
        "//tensorflow/lite/experimental/micro/testing:micro_test",
    ],
)
