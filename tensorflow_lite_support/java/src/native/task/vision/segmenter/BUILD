load("@org_tensorflow//tensorflow/lite:build_def.bzl", "tflite_jni_binary")

package(
    default_visibility = ["//tensorflow_lite_support:users"],
    licenses = ["notice"],  # Apache 2.0
)

exports_files(["image_segmenter_jni.cc"])

cc_library(
    name = "image_segmenter_native",
    srcs = [
        ":libtask_vision_jni.so",
    ],
)

tflite_jni_binary(
    name = "libtask_vision_jni.so",
    srcs = [
        "image_segmenter_jni.cc",
    ],
    deps = [
        "//tensorflow_lite_support/cc/port:statusor",
        "//tensorflow_lite_support/cc/task/vision:image_segmenter",
        "//tensorflow_lite_support/cc/task/vision/core:frame_buffer",
        "//tensorflow_lite_support/cc/task/vision/proto:image_segmenter_options_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/proto:segmentations_proto_inc",
        "//tensorflow_lite_support/cc/task/vision/utils:frame_buffer_common_utils",
        "//tensorflow_lite_support/cc/utils:jni_utils",
        "//tensorflow_lite_support/java/jni",
        "//tensorflow_lite_support/java/src/native/task/vision:jni_utils",
        "@com_google_absl//absl/strings",
    ],
)
