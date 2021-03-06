load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = [
        "auth.go",
        "cani.go",
        "reconcile.go",
    ],
    importpath = "k8s.io/kubernetes/pkg/kubectl/cmd/auth",
    visibility = [
        "//build/visible_to:pkg_kubectl_cmd_auth_CONSUMERS",
    ],
    deps = [
        "//pkg/apis/authorization:go_default_library",
        "//pkg/client/clientset_generated/internalclientset/typed/authorization/internalversion:go_default_library",
        "//pkg/kubectl/cmd/templates:go_default_library",
        "//pkg/kubectl/cmd/util:go_default_library",
        "//pkg/kubectl/genericclioptions:go_default_library",
        "//pkg/kubectl/genericclioptions/printers:go_default_library",
        "//pkg/kubectl/genericclioptions/resource:go_default_library",
        "//pkg/kubectl/scheme:go_default_library",
        "//pkg/registry/rbac/reconciliation:go_default_library",
        "//staging/src/k8s.io/api/rbac/v1:go_default_library",
        "//staging/src/k8s.io/api/rbac/v1alpha1:go_default_library",
        "//staging/src/k8s.io/api/rbac/v1beta1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/api/meta:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
        "//staging/src/k8s.io/client-go/kubernetes/typed/core/v1:go_default_library",
        "//staging/src/k8s.io/client-go/kubernetes/typed/rbac/v1:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/github.com/spf13/cobra:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = [
        "//build/visible_to:pkg_kubectl_cmd_auth_CONSUMERS",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["cani_test.go"],
    embed = [":go_default_library"],
    deps = [
        "//pkg/api/legacyscheme:go_default_library",
        "//pkg/kubectl/cmd/testing:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/runtime/schema:go_default_library",
        "//staging/src/k8s.io/client-go/rest:go_default_library",
        "//staging/src/k8s.io/client-go/rest/fake:go_default_library",
    ],
)
