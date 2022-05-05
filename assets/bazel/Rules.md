

## Rules

native rule随 Bazel 二进制文件一起提供，不需要`load`声明。本机规则在 BUILD 文件中全局可用。在 .bzl 文件中，您可以在`native`模块中找到它们。对于与 Bazel 分开发布的非原生 Starlark 规则，请参阅 [推荐规则](https://docs.bazel.build/versions/main/rules.html#recommended-rules)列表。

### Language-specific native rules

| Language        | Binary rules                                                 | Library rules                                                | Test rules                                                   | Other rules                                                  |
| :-------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| Android         | [android_binary](https://docs.bazel.build/versions/main/be/android.html#android_binary) | [aar_import](https://docs.bazel.build/versions/main/be/android.html#aar_import) [android_library](https://docs.bazel.build/versions/main/be/android.html#android_library) | [android_instrumentation_test](https://docs.bazel.build/versions/main/be/android.html#android_instrumentation_test) [android_local_test](https://docs.bazel.build/versions/main/be/android.html#android_local_test) | [android_device](https://docs.bazel.build/versions/main/be/android.html#android_device) [android_ndk_repository](https://docs.bazel.build/versions/main/be/android.html#android_ndk_repository) [android_sdk_repository](https://docs.bazel.build/versions/main/be/android.html#android_sdk_repository) |
| C / C++         | [cc_binary](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary) | [cc_import](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_import) [cc_library](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_library) [cc_proto_library](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_proto_library) [fdo_prefetch_hints](https://docs.bazel.build/versions/main/be/c-cpp.html#fdo_prefetch_hints) [fdo_profile](https://docs.bazel.build/versions/main/be/c-cpp.html#fdo_profile) [propeller_optimize](https://docs.bazel.build/versions/main/be/c-cpp.html#propeller_optimize) | [cc_test](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_test) | [cc_toolchain](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_toolchain) [cc_toolchain_suite](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_toolchain_suite) |
| Java            | [java_binary](https://docs.bazel.build/versions/main/be/java.html#java_binary) | [java_import](https://docs.bazel.build/versions/main/be/java.html#java_import) [java_library](https://docs.bazel.build/versions/main/be/java.html#java_library) [java_lite_proto_library](https://docs.bazel.build/versions/main/be/java.html#java_lite_proto_library) [java_proto_library](https://docs.bazel.build/versions/main/be/java.html#java_proto_library) | [java_test](https://docs.bazel.build/versions/main/be/java.html#java_test) | [java_package_configuration](https://docs.bazel.build/versions/main/be/java.html#java_package_configuration) [java_plugin](https://docs.bazel.build/versions/main/be/java.html#java_plugin) [java_runtime](https://docs.bazel.build/versions/main/be/java.html#java_runtime) [java_toolchain](https://docs.bazel.build/versions/main/be/java.html#java_toolchain) |
| Objective-C     | [apple_static_library](https://docs.bazel.build/versions/main/be/objective-c.html#apple_static_library) | [j2objc_library](https://docs.bazel.build/versions/main/be/objective-c.html#j2objc_library) [objc_import](https://docs.bazel.build/versions/main/be/objective-c.html#objc_import) [objc_library](https://docs.bazel.build/versions/main/be/objective-c.html#objc_library) |                                                              | [available_xcodes](https://docs.bazel.build/versions/main/be/objective-c.html#available_xcodes) [xcode_config](https://docs.bazel.build/versions/main/be/objective-c.html#xcode_config) [xcode_version](https://docs.bazel.build/versions/main/be/objective-c.html#xcode_version) |
| Protocol Buffer |                                                              | [proto_lang_toolchain](https://docs.bazel.build/versions/main/be/protocol-buffer.html#proto_lang_toolchain) [proto_library](https://docs.bazel.build/versions/main/be/protocol-buffer.html#proto_library) |                                                              |                                                              |
| Python          | [py_binary](https://docs.bazel.build/versions/main/be/python.html#py_binary) | [py_library](https://docs.bazel.build/versions/main/be/python.html#py_library) | [py_test](https://docs.bazel.build/versions/main/be/python.html#py_test) | [py_runtime](https://docs.bazel.build/versions/main/be/python.html#py_runtime) |
| Shell           | [sh_binary](https://docs.bazel.build/versions/main/be/shell.html#sh_binary) | [sh_library](https://docs.bazel.build/versions/main/be/shell.html#sh_library) | [sh_test](https://docs.bazel.build/versions/main/be/shell.html#sh_test) |                                                              |

### Language-agnostic native rules

| Family        | Rules                                                        |
| :------------ | :----------------------------------------------------------- |
| Extra Actions | [action_listener](https://docs.bazel.build/versions/main/be/extra-actions.html#action_listener) [extra_action](https://docs.bazel.build/versions/main/be/extra-actions.html#extra_action) |
| General       | [alias](https://docs.bazel.build/versions/main/be/general.html#alias) [config_setting](https://docs.bazel.build/versions/main/be/general.html#config_setting) [filegroup](https://docs.bazel.build/versions/main/be/general.html#filegroup) [genquery](https://docs.bazel.build/versions/main/be/general.html#genquery) [genrule](https://docs.bazel.build/versions/main/be/general.html#genrule) [test_suite](https://docs.bazel.build/versions/main/be/general.html#test_suite) |
| Platform      | [constraint_setting](https://docs.bazel.build/versions/main/be/platform.html#constraint_setting) [constraint_value](https://docs.bazel.build/versions/main/be/platform.html#constraint_value) [platform](https://docs.bazel.build/versions/main/be/platform.html#platform) [toolchain](https://docs.bazel.build/versions/main/be/platform.html#toolchain) [toolchain_type](https://docs.bazel.build/versions/main/be/platform.html#toolchain_type) |
| Workspace     | [bind](https://docs.bazel.build/versions/main/be/workspace.html#bind) [local_repository](https://docs.bazel.build/versions/main/be/workspace.html#local_repository) [new_local_repository](https://docs.bazel.build/versions/main/be/workspace.html#new_local_repository) |

# C / C++ 规则

## 规则

- [cc_binary](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary)
- [cc_import](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_import)
- [cc_library](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_library)
- [cc_proto_library](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_proto_library)
- [fdo_prefetch_hints](https://docs.bazel.build/versions/main/be/c-cpp.html#fdo_prefetch_hints)
- [fdo_profile](https://docs.bazel.build/versions/main/be/c-cpp.html#fdo_profile)
- [propeller_optimize](https://docs.bazel.build/versions/main/be/c-cpp.html#propeller_optimize)
- [cc_test](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_test)
- [cc_toolchain](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_toolchain)
- [cc_toolchain_suite](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_toolchain_suite)

## cc_binary

```
cc_binary(name, deps, srcs, data, additional_linker_inputs, args, compatible_with, copts, defines, deprecation, distribs, env, exec_compatible_with, exec_properties, features, includes, licenses, linkopts, linkshared, linkstatic, local_defines, malloc, nocopts, output_licenses, restricted_to, stamp, tags, target_compatible_with, testonly, toolchains, visibility, win_def_file)
```

#### 隐式输出目标

- `name.stripped`（仅在明确要求时构建）：二进制文件的剥离版本。`strip -g`在二进制文件上运行以删除调试符号。可以在命令行上使用 `--stripopt=-foo`. 仅在明确请求时才构建此输出。
- `name.dwp`（仅在明确要求时构建）：如果 启用了[Fission](https://gcc.gnu.org/wiki/DebugFission)：适用于调试远程部署的二进制文件的调试信息包文件。否则：一个空文件。

### 论据

| 属性                       |                                                              |
| :------------------------- | ------------------------------------------------------------ |
| `name`                     | `Name; required`此目标的唯一名称。                           |
| `deps`                     | `List of labels; optional`要链接到二进制目标的其他库的列表。`cc_library`这些可以是`objc_library` 目标。 |
| `srcs`                     | `List of labels; optional`为创建目标而处理的 C 和 C++ 文件的列表。这些是 C/C++ 源文件和头文件，可以是非生成的（正常源代码），也可以是生成的。将编译所有`.cc`、`.c`和文件。`.cpp`这些可能是生成的文件：如果命名文件在`outs`某个其他规则中，则该规则将自动依赖于该其他规则。文件`.h`不会被编译，但可以被源包含在此规则中。`.cc`和 文件都`.h`可以直接包含在这些`srcs`或参数中`hdrs`列出的任何规则中列出的标题`deps`。所有`#include`的 d 文件都必须在 `srcs`这个规则的属性中被提及，或者在被 `hdrs`引用`cc_library()`的 s 的属性中。推荐的样式是与要在该库的`hdrs`属性中列出的库关联的标头，以及与此规则的源关联的任何剩余标头在 中列出 `srcs`。 有关更详细的说明， 请参阅[“标头包含检查” 。](https://docs.bazel.build/versions/main/be/c-cpp.html#hdrs)如果规则的名称在 中`srcs`，则该规则自动依赖于该规则。如果命名规则`outs`是 C 或 C++ 源文件，则将它们编译到此规则中；如果它们是库文件，则它们被链接。允许的`srcs`文件类型：C 和 C++ 源文件：`.c`, `.cc`, `.cpp`, `.cxx`, `.c++`,`.C`C 和 C++ 头文件：`.h`, `.hh`, `.hpp`, `.hxx`, `.inc`, `.inl`,`.H`带有 C 预处理器的汇编程序：`.S`存档：`.a`，`.pic.a`“始终链接”库：`.lo`，`.pic.lo`共享库，版本化或非版本化：`.so`， `.so.*version*`目标文件：`.o`,`.pic.o`...以及产生这些文件的任何规则。根据 gcc 约定，不同的扩展表示不同的编程语言。 |
| `additional_linker_inputs` | `List of labels; optional`将这些文件传递给 C++ 链接器命令。例如，可以在此处提供已编译的 Windows .res 文件以嵌入到二进制目标中。 |
| `copts`                    | `List of strings; optional`将这些选项添加到 C++ 编译命令。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。`COPTS`在编译二进制目标之前 ，此属性中的每个字符串都按给定顺序添加。这些标志只对编译这个目标生效，而不是它的依赖项，所以要小心其他地方包含的头文件。所有路径都应该相对于工作空间，而不是当前包。如果包声明了该[特性](https://docs.bazel.build/versions/main/be/functions.html#package.features) `no_copts_tokenization`，则 Bourne shell 标记化仅适用于由单个“Make”变量组成的字符串。 |
| `defines`                  | `List of strings; optional`要添加到编译行的定义列表。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。每个必须由单个 Bourne shell 令牌组成的字符串都被添加`-D`到该目标的编译命令行以及依赖它的每个规则中。要非常小心，因为这可能会产生深远的影响。如有疑问，请 [`local_defines`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.local_defines)改为添加定义值。 |
| `includes`                 | `List of strings; optional`要添加到编译行的包含目录列表。以[“使变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。每个字符串都以 . 开头`-isystem`并添加到`COPTS`. 与[COPTS](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)不同，这些标志是为该规则和依赖它的每个规则添加的。（注意：不是它所依赖的规则！）要非常小心，因为这可能会产生深远的影响。如有疑问，请将“-I”标志添加到[COPTS](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)。标头必须添加到 srcs 或 hdrs，否则当编译为沙盒（默认）时，它们将不可用于依赖规则。 |
| `linkopts`                 | `List of strings; optional`将这些标志添加到 C++ 链接器命令。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换、 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)和 [标签扩展](https://docs.bazel.build/versions/main/be/common-definitions.html#label-expansion)。`LINKOPTS`在链接二进制目标之前， 会添加此属性中的每个字符串。此列表中不以 开头`$`或`-`假定为 中目标的标签的每个元素`deps`。该目标生成的文件列表附加到链接器选项中。如果标签无效，或未在 中声明，则会报告错误`deps`。 |
| `linkshared`               | `Boolean; optional; nonconfigurable; default is False`创建一个共享库。要启用此属性，请包含`linkshared=True`在您的规则中。默认情况下，此选项处于关闭状态。这个标志的存在意味着与`-shared`标志的链接发生`gcc`，并且生成的共享库适合加载到例如Java程序中。但是，出于构建目的，它永远不会链接到依赖二进制文件，因为假设使用 [cc_binary](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary)规则构建的共享库仅由其他程序手动加载，因此不应将其视为[cc_library](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_library) 规则的替代品。为了可扩展性，我们建议完全避免这种方法，而是简单地`java_library`依赖`cc_library`规则。如果同时指定`linkopts=['-static']`和`linkshared=True`，您将获得一个完全独立的单元。如果同时指定 `linkstatic=1`和`linkshared=True`，您将获得一个主要是独立的单元。 |
| `linkstatic`               | `Boolean; optional; default is True`For [`cc_binary`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary)and [`cc_test`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_test): 以静态模式链接二进制文件。对于`cc_library.linkstatic`：见下文。默认情况下，此选项对`cc_binary`其余部分打开和关闭。如果启用并且这是一个二进制文件或测试，则此选项会告诉构建工具尽可能链接 用户库`.a`的 's 而不是`.so`'s。一些系统库可能仍然是动态链接的，没有静态库的库也是如此。因此生成的可执行文件仍将是动态链接的，因此*大部分是*静态的。实际上有三种不同的方式来链接可执行文件：具有fully_static_link功能的STATIC，其中所有内容都是静态链接的；例如“ `gcc -static foo.o libbar.a libbaz.a -lm`”。通过在 属性中 指定来启用此模式。`fully_static_link`[`features`](https://docs.bazel.build/versions/main/be/common-definitions.html#features)STATIC，其中所有用户库都是静态链接的（如果有静态版本可用），但系统库（不包括 C/C++ 运行时库）是动态链接的，例如“ `gcc foo.o libfoo.a libbaz.a -lm`”。 通过指定启用此模式`linkstatic=True`。DYNAMIC，其中所有库都是动态链接的（如果有动态版本可用），例如“ `gcc foo.o libfoo.so libbaz.so -lm`”。 通过指定启用此模式`linkstatic=False`。如果在规则上使用该属性，则 该`linkstatic`属性具有不同的含义 。[`cc_library()`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_library)对于 C++ 库，`linkstatic=True`表示只允许静态链接，因此不会`.so`生成。linkstatic=False 不会阻止创建静态库。该属性旨在控制动态库的创建。如果`linkstatic=False`，则构建工具将创建指向该区域中依赖的共享库的符号链接`*.runfiles`。 |
| `local_defines`            | `List of strings; optional`要添加到编译行的定义列表。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。每个必须由单个 Bourne shell 标记组成的字符串都被`-D`添加到该目标的编译命令行中，但不添加到它的依赖项中。 |
| `malloc`                   | `Label; optional; default is @bazel_tools//tools/cpp:malloc`覆盖对 malloc 的默认依赖项。默认情况下，C++ 二进制文件链接到`//tools/cpp:malloc`，这是一个空库，因此二进制文件最终使用 libc malloc。此标签必须引用一个`cc_library`. 如果编译是针对非 C++ 规则的，则此选项无效。如果指定，则忽略此属性的值 `linkshared=True`。 |
| `nocopts`                  | `String; optional`从 C++ 编译命令中删除匹配选项。以[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。此属性的值被解释为正则表达式。任何`COPTS`与此正则表达式匹配的预先存在的内容（包括在规则的[copts](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)属性中明确指定的值）都将被删除， `COPTS`以便编译此规则。这个属性应该很少需要。 |
| `stamp`                    | `Integer; optional; default is -1`是否将构建信息编码到二进制文件中。可能的值：`stamp = 1`：始终将构建信息标记到二进制文件中，即使在 [`--nostamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)构建中也是如此。**应该避免此设置**，因为它可能会杀死二进制文件的远程缓存以及依赖它的任何下游操作。`stamp = 0`：始终用常量值替换构建信息。这提供了良好的构建结果缓存。`stamp = -1`：构建信息的嵌入由 [`--[no\]stamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)标志控制。*除非它们的依赖关系发生变化，否则不会*重建标记的二进制文件。 |
| `win_def_file`             | `Label; optional`要传递给链接器的 Windows DEF 文件。仅当 Windows 是目标平台时才应使用此属性。它可用于在链接共享库期间[ 导出符号。](https://msdn.microsoft.com/en-us/library/d91k01sh.aspx) |

## cc_import

```
cc_import(name, data, hdrs, alwayslink, compatible_with, deprecation, distribs, features, interface_library, licenses, restricted_to, shared_library, static_library, system_provided, tags, target_compatible_with, testonly, visibility)
```

`cc_import`规则允许用户导入预编译的 C/C++ 库。

以下是典型用例：

以下是典型用例：

1. 链接静态库

```
cc_import(
  name = "mylib",
  hdrs = ["mylib.h"],
  static_library = "libmylib.a",
  # If alwayslink is turned on,
  # libmylib.a will be forcely linked into any binary that depends on it.
  # alwayslink = 1,
)
```

 2.链接共享库（Unix）

```
cc_import(
  name = "mylib",
  hdrs = ["mylib.h"],
  shared_library = "libmylib.so",
)
```

3. 将共享库与接口库链接（Windows）

```
cc_import(
  name = "mylib",
  hdrs = ["mylib.h"],
  # mylib.lib is a import library for mylib.dll which will be passed to linker
  interface_library = "mylib.lib",
  # mylib.dll will be available for runtime
  shared_library = "mylib.dll",
)
```

4. 与（Windows） 链接共享库`system_provided=True`

```
cc_import(
  name = "mylib",
  hdrs = ["mylib.h"],
  # mylib.lib is an import library for mylib.dll which will be passed to linker
  interface_library = "mylib.lib",
  # mylib.dll is provided by system environment, for example it can be found in PATH.
  # This indicates that Bazel is not responsible for making mylib.dll available.
  system_provided = 1,
)
```


5.在 Unix 上 链接到静态或共享库：

```
cc_import(
  name = "mylib",
  hdrs = ["mylib.h"],
  static_library = "libmylib.a",
  shared_library = "libmylib.so",
)

# first will link to libmylib.a
cc_binary(
  name = "first",
  srcs = ["first.cc"],
  deps = [":mylib"],
  linkstatic = 1, # default value
)

# second will link to libmylib.so
cc_binary(
  name = "second",
  srcs = ["second.cc"],
  deps = [":mylib"],
  linkstatic = 0,
)
```

在 Windows 上：

```
cc_import(
  name = "mylib",
  hdrs = ["mylib.h"],
  static_library = "libmylib.lib", # A normal static library
  interface_library = "mylib.lib", # An import library for mylib.dll
  shared_library = "mylib.dll",
)

# first will link to libmylib.lib
cc_binary(
  name = "first",
  srcs = ["first.cc"],
  deps = [":mylib"],
  linkstatic = 1, # default value
)

# second will link to mylib.dll through mylib.lib
cc_binary(
  name = "second",
  srcs = ["second.cc"],
  deps = [":mylib"],
  linkstatic = 0,
)
```



### 参数

| 属性                |                                                              |
| :------------------ | ------------------------------------------------------------ |
| `name`              | `Name; required`此目标的唯一名称。                           |
| `hdrs`              | `List of labels; optional`此预编译库发布的头文件列表将直接包含在依赖规则中的源中。 |
| `alwayslink`        | `Boolean; optional; default is False`如果为 1，任何依赖（直接或间接）此 C++ 预编译库的二进制文件都将链接到静态库中存档的所有目标文件，即使其中一些文件不包含二进制文件引用的符号。如果您的代码没有被二进制代码显式调用，这很有用，例如，如果您的代码注册以接收某些服务提供的某些回调。如果 alwayslink 在 Windows 上无法与 VS 2017 一起使用，这是由于 [已知问题](https://github.com/bazelbuild/bazel/issues/3949)，请将您的 VS 2017 升级到最新版本。 |
| `interface_library` | `Label; optional`用于链接共享库的单个接口库。允许的文件类型 ：`.ifso`、 `.tbd`、 `.lib`或 `.so``.dylib` |
| `shared_library`    | `Label; optional`单个预编译共享库。Bazel 确保它在运行时可用于依赖它的二进制文件。允许的文件类型： `.so`, `.dll` 或`.dylib` |
| `static_library`    | `Label; optional`一个预编译的静态库。允许的文件类型： `.a`, `.pic.a` 或`.lib` |
| `system_provided`   | `Boolean; optional; default is False`如果为1，则表示运行时需要的共享库由系统提供。在这种情况下，`interface_library`应该指定并且 `shared_library`应该为空。 |

## cc_library

```
cc_library(name, deps, srcs, data, hdrs, alwayslink, compatible_with, copts, defines, deprecation, distribs, exec_compatible_with, exec_properties, features, implementation_deps, include_prefix, includes, licenses, linkopts, linkstamp, linkstatic, local_defines, nocopts, restricted_to, strip_include_prefix, tags, target_compatible_with, testonly, textual_hdrs, toolchains, visibility, win_def_file)
```

#### 标头包含检查

构建中使用的所有头文件都必须在`hdrs`or `srcs`of`cc_*`规则中声明。这是强制执行的。

对于`cc_library`规则，头文件包含库的`hdrs`公共接口，并且可以直接包含在库中的文件`hdrs`和 `srcs`库本身的文件中，也可以从`hdrs`在 其. 头文件只能直接包含在库本身的文件 中。在决定是否将标头放入 or时，您应该询问是否希望该库的使用者能够直接包含它。这与编程语言中的可见性 之间的决定大致相同 。`srcs``cc_*``deps``srcs``hdrs``srcs``hdrs``srcs``public``private`

`cc_binary`和`cc_test`规则没有导出接口，因此它们也没有`hdrs`属性。属于二进制文件或直接测试的所有头文件都应列在`srcs`.

为了说明这些规则，请看以下示例。

```
cc_binary(
    name = "foo",
    srcs = [
        "foo.cc",
        "foo.h",
    ],
    deps = [":bar"],
)

cc_library(
    name = "bar",
    srcs = [
        "bar.cc",
        "bar-impl.h",
    ],
    hdrs = ["bar.h"],
    deps = [":baz"],
)

cc_library(
    name = "baz",
    srcs = [
        "baz.cc",
        "baz-impl.h",
    ],
    hdrs = ["baz.h"],
)
```

此示例中允许的直接包含列在下表中。例如 `foo.cc`允许直接包含`foo.h`and `bar.h`，但不允许`baz.h`。

| Including file | Allowed inclusions     |
| :------------- | :--------------------- |
| foo.h          | bar.h                  |
| foo.cc         | foo.h bar.h            |
| bar.h          | bar-impl.h baz.h       |
| bar-impl.h     | bar.h baz.h            |
| bar.cc         | bar.h bar-impl.h baz.h |
| baz.h          | baz-impl.h             |
| baz-impl.h     | baz.h                  |
| baz.cc         | baz.h baz-impl.h       |

包含检查规则仅适用于*直接* 包含。在上面的例子中，`foo.cc`被允许包含`bar.h`，其中可能包含`baz.h`，而后者又被允许包含`baz-impl.h`。从技术上讲，文件的编译可以在传递闭包中或在任何传递闭包`.cc`中传递地包含任何头文件。在这种情况下，编译器可以在编译 时读取和，但不能包含. 为此，必须将其添加到 of 中。 `hdrs``srcs``cc_library``deps``baz.h``baz-impl.h``foo.cc``foo.cc``#include "baz.h"``baz``deps``foo`

不幸的是，Bazel 目前无法区分直接包含和传递包含，因此它无法检测文件非法直接包含仅允许传递包含的标头的错误情况。例如，如果在上面的示例中`foo.cc`直接包含`baz.h`. 这将是非法的，因为`foo` 不直接依赖于`baz`. 目前，这种情况下不会产生错误，但将来可能会添加此类错误检查。

### 参数

| 属性                   |                                                              |
| :--------------------- | ------------------------------------------------------------ |
| `name`                 | `Name; required`此目标的唯一名称。                           |
| `deps`                 | `List of labels; optional`要链接到二进制目标的其他库的列表。`cc_library`这些可以是`objc_library` 目标。 |
| `srcs`                 | `List of labels; optional`为创建目标而处理的 C 和 C++ 文件的列表。这些是 C/C++ 源文件和头文件，可以是非生成的（正常源代码），也可以是生成的。将编译所有`.cc`、`.c`和文件。`.cpp`这些可能是生成的文件：如果命名文件在`outs`某个其他规则中，则该规则将自动依赖于该其他规则。文件`.h`不会被编译，但可以被源包含在此规则中。`.cc`和 文件都`.h`可以直接包含在这些`srcs`或参数中`hdrs`列出的任何规则中列出的标题`deps`。所有`#include`的 d 文件都必须在 `srcs`这个规则的属性中被提及，或者在被 `hdrs`引用`cc_library()`的 s 的属性中。推荐的样式是与要在该库的`hdrs`属性中列出的库关联的标头，以及与此规则的源关联的任何剩余标头在 中列出 `srcs`。 有关更详细的说明， 请参阅[“标头包含检查” 。](https://docs.bazel.build/versions/main/be/c-cpp.html#hdrs)如果规则的名称在 中`srcs`，则该规则自动依赖于该规则。如果命名规则`outs`是 C 或 C++ 源文件，则将它们编译到此规则中；如果它们是库文件，则它们被链接。允许的`srcs`文件类型：C 和 C++ 源文件：`.c`, `.cc`, `.cpp`, `.cxx`, `.c++`,`.C`C 和 C++ 头文件：`.h`, `.hh`, `.hpp`, `.hxx`, `.inc`, `.inl`,`.H`带有 C 预处理器的汇编程序：`.S`存档：`.a`，`.pic.a`“始终链接”库：`.lo`，`.pic.lo`共享库，版本化或非版本化：`.so`， `.so.*version*`目标文件：`.o`,`.pic.o`...以及产生这些文件的任何规则。根据 gcc 约定，不同的扩展表示不同的编程语言。 |
| `hdrs`                 | `List of labels; optional`由该库发布的头文件列表，这些头文件将直接包含在依赖规则中的源中。这是声明描述库接口的头文件的首选位置。这些标头将可供源包含在此规则或从属规则中。不应由该库的客户端包含的标头应列在`srcs`属性中，即使它们包含在已发布的标头中。有关更详细的说明，请参阅[“标头包含检查” 。](https://docs.bazel.build/versions/main/be/c-cpp.html#hdrs) |
| `alwayslink`           | `Boolean; optional; default is False`如果为 1，任何依赖（直接或间接）此 C++ 库的二进制文件都将链接到 中列出的文件的所有目标文件 `srcs`，即使其中一些不包含二进制文件引用的符号。如果您的代码没有被二进制代码显式调用，这很有用，例如，如果您的代码注册以接收某些服务提供的某些回调。如果 alwayslink 在 Windows 上无法与 VS 2017 一起使用，这是由于 [已知问题](https://github.com/bazelbuild/bazel/issues/3949)，请将您的 VS 2017 升级到最新版本。 |
| `copts`                | `List of strings; optional`将这些选项添加到 C++ 编译命令。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。`COPTS`在编译二进制目标之前 ，此属性中的每个字符串都按给定顺序添加。这些标志只对编译这个目标生效，而不是它的依赖项，所以要小心其他地方包含的头文件。所有路径都应该相对于工作空间，而不是当前包。如果包声明了该[特性](https://docs.bazel.build/versions/main/be/functions.html#package.features) `no_copts_tokenization`，则 Bourne shell 标记化仅适用于由单个“Make”变量组成的字符串。 |
| `defines`              | `List of strings; optional`要添加到编译行的定义列表。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。每个必须由单个 Bourne shell 令牌组成的字符串都被添加`-D`到该目标的编译命令行以及依赖它的每个规则中。要非常小心，因为这可能会产生深远的影响。如有疑问，请 [`local_defines`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.local_defines)改为添加定义值。 |
| `implementation_deps`  | `List of labels; optional`库目标所依赖的其他库的列表。与 with 不同 `deps`，这些库（以及它们所有的传递依赖）的头文件和包含路径仅用于编译该库，而不是依赖于它的库。指定的库`implementation_deps`仍然链接在依赖于该库的二进制目标中。目前使用仅限于 cc_libraries 并由 flag 保护 `--experimental_cc_implementation_deps`。 |
| `include_prefix`       | `String; optional`添加到此规则标头路径的前缀。设置后，`hdrs`此规则的属性中的标头可通过附加到其存储库相对路径的此属性的值访问。在`strip_include_prefix`添加此前缀之前删除属性中的前缀。 |
| `includes`             | `List of strings; optional`要添加到编译行的包含目录列表。以[“使变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。每个字符串都以 . 开头`-isystem`并添加到`COPTS`. 与[COPTS](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)不同，这些标志是为该规则和依赖它的每个规则添加的。（注意：不是它所依赖的规则！）要非常小心，因为这可能会产生深远的影响。如有疑问，请将“-I”标志添加到[COPTS](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)。标头必须添加到 srcs 或 hdrs，否则当编译为沙盒（默认）时，它们将不可用于依赖规则。 |
| `linkopts`             | `List of strings; optional`将这些标志添加到 C++ 链接器命令。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换、 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)和 [标签扩展](https://docs.bazel.build/versions/main/be/common-definitions.html#label-expansion)。`LINKOPTS`在链接二进制目标之前， 会添加此属性中的每个字符串。此列表中不以 开头`$`或`-`假定为 中目标的标签的每个元素`deps`。该目标生成的文件列表附加到链接器选项中。如果标签无效，或未在 中声明，则会报告错误`deps`。 |
| `linkstamp`            | `Label; optional`同时将指定的 C++ 源文件编译并链接到最终的二进制文件中。将时间戳信息引入二进制文件需要这种技巧；如果我们以通常的方式将源文件编译为目标文件，则时间戳将不正确。linkstamp 编译可能不包括任何特定的编译器标志集，因此不应依赖于任何特定的头文件、编译器选项或其他构建变量。 *这个选项应该只在 `base`包中需要。* |
| `linkstatic`           | `Boolean; optional; default is False`For [`cc_binary`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary)and [`cc_test`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_test): 以静态模式链接二进制文件。对于`cc_library.linkstatic`：见下文。默认情况下，此选项对`cc_binary`其余部分打开和关闭。如果启用并且这是一个二进制文件或测试，则此选项会告诉构建工具尽可能链接 用户库`.a`的 's 而不是`.so`'s。一些系统库可能仍然是动态链接的，没有静态库的库也是如此。因此生成的可执行文件仍将是动态链接的，因此*大部分是*静态的。实际上有三种不同的方式来链接可执行文件：具有fully_static_link功能的STATIC，其中所有内容都是静态链接的；例如“ `gcc -static foo.o libbar.a libbaz.a -lm`”。通过在 属性中 指定来启用此模式。`fully_static_link`[`features`](https://docs.bazel.build/versions/main/be/common-definitions.html#features)STATIC，其中所有用户库都是静态链接的（如果有静态版本可用），但系统库（不包括 C/C++ 运行时库）是动态链接的，例如“ `gcc foo.o libfoo.a libbaz.a -lm`”。 通过指定启用此模式`linkstatic=True`。DYNAMIC，其中所有库都是动态链接的（如果有动态版本可用），例如“ `gcc foo.o libfoo.so libbaz.so -lm`”。 通过指定启用此模式`linkstatic=False`。如果在规则上使用该属性，则 该`linkstatic`属性具有不同的含义 。[`cc_library()`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_library)对于 C++ 库，`linkstatic=True`表示只允许静态链接，因此不会`.so`生成。linkstatic=False 不会阻止创建静态库。该属性旨在控制动态库的创建。如果`linkstatic=False`，则构建工具将创建指向该区域中依赖的共享库的符号链接`*.runfiles`。 |
| `local_defines`        | `List of strings; optional`要添加到编译行的定义列表。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。每个必须由单个 Bourne shell 标记组成的字符串都被`-D`添加到该目标的编译命令行中，但不添加到它的依赖项中。 |
| `nocopts`              | `String; optional`从 C++ 编译命令中删除匹配选项。以[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。此属性的值被解释为正则表达式。任何`COPTS`与此正则表达式匹配的预先存在的内容（包括在规则的[copts](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)属性中明确指定的值）都将被删除， `COPTS`以便编译此规则。这个属性应该很少需要。 |
| `strip_include_prefix` | `String; optional`从该规则的标头路径中去除的前缀。设置后，`hdrs`此规则的属性中的标头可在其路径中访问，并切断此前缀。如果它是相对路径，则将其视为相对于包的路径。如果是绝对路径，则将其理解为存储库相对路径。属性中的`include_prefix`前缀是在去除此前缀之后添加的。 |
| `textual_hdrs`         | `List of labels; optional`此库发布的头文件列表，以文本形式包含在依赖规则中的源中。这是声明无法自行编译的头文件的位置；也就是说，它们总是需要被其他源文件以文本形式包含以构建有效的代码。 |
| `win_def_file`         | `Label; optional`要传递给链接器的 Windows DEF 文件。仅当 Windows 是目标平台时才应使用此属性。它可用于在链接共享库期间[ 导出符号。](https://msdn.microsoft.com/en-us/library/d91k01sh.aspx) |

## cc_proto_library

```
cc_proto_library(name, deps, data, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, features, licenses, restricted_to, tags, target_compatible_with, testonly, visibility)
```

`cc_proto_library``.proto`从文件 生成 C++ 代码。

`deps`必须指向[`proto_library `](https://docs.bazel.build/versions/main/be/protocol-buffer.html#proto_library)规则。

例子：

```
cc_library(
    name = "lib",
    deps = [":foo_cc_proto"],
)

cc_proto_library(
    name = "foo_cc_proto",
    deps = [":foo_proto"],
)

proto_library(
    name = "foo_proto",
)
```

### 论据

| 属性   |                                                              |
| :----- | ------------------------------------------------------------ |
| `name` | `Name; required`此目标的唯一名称。                           |
| `deps` | `List of labels; optional`[`proto_library`](https://docs.bazel.build/versions/main/be/protocol-buffer.html#proto_library) 为其生成 C++ 代码 的规则列表。 |

## fdo_prefetch_hints

```
fdo_prefetch_hints(name, compatible_with, deprecation, distribs, features, licenses, profile, restricted_to, tags, target_compatible_with, testonly, visibility)
```

表示位于工作区或指定绝对路径中的 FDO 预取提示配置文件。例子：

```
fdo_prefetch_hints(
    name = "hints",
    profile = "//path/to/hints:profile.afdo",
)

fdo_profile(
  name = "hints_abs",
  absolute_path_profile = "/absolute/path/profile.afdo",
)
```

### 参数

| 属性      |                                                              |
| :-------- | ------------------------------------------------------------ |
| `name`    | `Name; required`此目标的唯一名称。                           |
| `profile` | `Label; optional`提示配置文件的标签。提示文件具有 .afdo 扩展名。标签还可以指向 fdo_absolute_path_profile 规则。 |

## fdo_profile

```
fdo_profile(name, absolute_path_profile, compatible_with, deprecation, distribs, features, licenses, profile, proto_profile, restricted_to, tags, target_compatible_with, testonly, visibility)
```

表示位于工作区或指定绝对路径中的 FDO 配置文件。例子：

```
fdo_profile(
    name = "fdo",
    profile = "//path/to/fdo:profile.zip",
)

fdo_profile(
  name = "fdo_abs",
  absolute_path_profile = "/absolute/path/profile.zip",
)
```

### 参数

| 属性                    |                                                              |
| :---------------------- | ------------------------------------------------------------ |
| `name`                  | `Name; required`此目标的唯一名称。                           |
| `absolute_path_profile` | `String; optional`FDO 配置文件的绝对路径。FDO 文件可能只有 .afdo 扩展名。 |
| `profile`               | `Label; optional`FDO 配置文件的标签。FDO 文件可以具有以下扩展名之一：.profraw 用于未索引的 LLVM 配置文件，.profdata 用于索引 LLVM 配置文件，.zip 包含 LLVM profraw 配置文件，.afdo 用于 AutoFDO 配置文件，.xfdo 用于 XBinary 配置文件。标签还可以指向 fdo_absolute_path_profile 规则。 |
| `proto_profile`         | `Label; optional`protobuf 配置文件的标签。                   |

## propeller_optimize

```
propeller_optimize(name, compatible_with, deprecation, distribs, features, ld_profile, licenses, restricted_to, tags, target_compatible_with, testonly, visibility)
```

表示工作区中的 Propeller 优化配置文件。例子：

```
propeller_optimize(
    name = "layout",
    cc_profile = "//path:cc_profile.txt",
    ld_profile = "//path:ld_profile.txt"
)

propeller_optimize(
    name = "layout_absolute",
    absolute_cc_profile = "/absolute/cc_profile.txt",
    absolute_ld_profile = "/absolute/ld_profile.txt"
)
```

### 参数

| 属性         |                                                              |
| :----------- | ------------------------------------------------------------ |
| `name`       | `Name; required`此目标的唯一名称。                           |
| `ld_profile` | `Label; optional`传递给链接操作的配置文件的标签。此文件具有 .txt 扩展名。 |

## cc_test

```
cc_test(name, deps, srcs, data, additional_linker_inputs, args, compatible_with, copts, defines, deprecation, distribs, env, env_inherit, exec_compatible_with, exec_properties, features, flaky, includes, licenses, linkopts, linkstatic, local, local_defines, malloc, nocopts, restricted_to, shard_count, size, stamp, tags, target_compatible_with, testonly, timeout, toolchains, visibility, win_def_file)
```

### 参数

| 属性                       |                                                              |
| :------------------------- | ------------------------------------------------------------ |
| `name`                     | `Name; required`此目标的唯一名称。                           |
| `deps`                     | `List of labels; optional`要链接到二进制目标的其他库的列表。`cc_library`这些可以是`objc_library` 目标。 |
| `srcs`                     | `List of labels; optional`为创建目标而处理的 C 和 C++ 文件的列表。这些是 C/C++ 源文件和头文件，可以是非生成的（正常源代码），也可以是生成的。将编译所有`.cc`、`.c`和文件。`.cpp`这些可能是生成的文件：如果命名文件在`outs`某个其他规则中，则该规则将自动依赖于该其他规则。文件`.h`不会被编译，但可以被源包含在此规则中。`.cc`和 文件都`.h`可以直接包含在这些`srcs`或参数中`hdrs`列出的任何规则中列出的标题`deps`。所有`#include`的 d 文件都必须在 `srcs`这个规则的属性中被提及，或者在被 `hdrs`引用`cc_library()`的 s 的属性中。推荐的样式是与要在该库的`hdrs`属性中列出的库关联的标头，以及与此规则的源关联的任何剩余标头在 中列出 `srcs`。 有关更详细的说明， 请参阅[“标头包含检查” 。](https://docs.bazel.build/versions/main/be/c-cpp.html#hdrs)如果规则的名称在 中`srcs`，则该规则自动依赖于该规则。如果命名规则`outs`是 C 或 C++ 源文件，则将它们编译到此规则中；如果它们是库文件，则它们被链接。允许的`srcs`文件类型：C 和 C++ 源文件：`.c`, `.cc`, `.cpp`, `.cxx`, `.c++`,`.C`C 和 C++ 头文件：`.h`, `.hh`, `.hpp`, `.hxx`, `.inc`, `.inl`,`.H`带有 C 预处理器的汇编程序：`.S`存档：`.a`，`.pic.a`“始终链接”库：`.lo`，`.pic.lo`共享库，版本化或非版本化：`.so`， `.so.*version*`目标文件：`.o`,`.pic.o`...以及产生这些文件的任何规则。根据 gcc 约定，不同的扩展表示不同的编程语言。 |
| `additional_linker_inputs` | `List of labels; optional`将这些文件传递给 C++ 链接器命令。例如，可以在此处提供已编译的 Windows .res 文件以嵌入到二进制目标中。 |
| `copts`                    | `List of strings; optional`将这些选项添加到 C++ 编译命令。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。`COPTS`在编译二进制目标之前 ，此属性中的每个字符串都按给定顺序添加。这些标志只对编译这个目标生效，而不是它的依赖项，所以要小心其他地方包含的头文件。所有路径都应该相对于工作空间，而不是当前包。如果包声明了该[特性](https://docs.bazel.build/versions/main/be/functions.html#package.features) `no_copts_tokenization`，则 Bourne shell 标记化仅适用于由单个“Make”变量组成的字符串。 |
| `defines`                  | `List of strings; optional`要添加到编译行的定义列表。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。每个必须由单个 Bourne shell 令牌组成的字符串都被添加`-D`到该目标的编译命令行以及依赖它的每个规则中。要非常小心，因为这可能会产生深远的影响。如有疑问，请 [`local_defines`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.local_defines)改为添加定义值。 |
| `includes`                 | `List of strings; optional`要添加到编译行的包含目录列表。以[“使变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。每个字符串都以 . 开头`-isystem`并添加到`COPTS`. 与[COPTS](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)不同，这些标志是为该规则和依赖它的每个规则添加的。（注意：不是它所依赖的规则！）要非常小心，因为这可能会产生深远的影响。如有疑问，请将“-I”标志添加到[COPTS](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)。标头必须添加到 srcs 或 hdrs，否则当编译为沙盒（默认）时，它们将不可用于依赖规则。 |
| `linkopts`                 | `List of strings; optional`将这些标志添加到 C++ 链接器命令。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换、 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)和 [标签扩展](https://docs.bazel.build/versions/main/be/common-definitions.html#label-expansion)。`LINKOPTS`在链接二进制目标之前， 会添加此属性中的每个字符串。此列表中不以 开头`$`或`-`假定为 中目标的标签的每个元素`deps`。该目标生成的文件列表附加到链接器选项中。如果标签无效，或未在 中声明，则会报告错误`deps`。 |
| `linkstatic`               | `Boolean; optional; default is False`For [`cc_binary`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary)and [`cc_test`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_test): 以静态模式链接二进制文件。对于`cc_library.linkstatic`：见下文。默认情况下，此选项对`cc_binary`其余部分打开和关闭。如果启用并且这是一个二进制文件或测试，则此选项会告诉构建工具尽可能链接 用户库`.a`的 's 而不是`.so`'s。一些系统库可能仍然是动态链接的，没有静态库的库也是如此。因此生成的可执行文件仍将是动态链接的，因此*大部分是*静态的。实际上有三种不同的方式来链接可执行文件：具有fully_static_link功能的STATIC，其中所有内容都是静态链接的；例如“ `gcc -static foo.o libbar.a libbaz.a -lm`”。通过在 属性中 指定来启用此模式。`fully_static_link`[`features`](https://docs.bazel.build/versions/main/be/common-definitions.html#features)STATIC，其中所有用户库都是静态链接的（如果有静态版本可用），但系统库（不包括 C/C++ 运行时库）是动态链接的，例如“ `gcc foo.o libfoo.a libbaz.a -lm`”。 通过指定启用此模式`linkstatic=True`。DYNAMIC，其中所有库都是动态链接的（如果有动态版本可用），例如“ `gcc foo.o libfoo.so libbaz.so -lm`”。 通过指定启用此模式`linkstatic=False`。如果在规则上使用该属性，则 该`linkstatic`属性具有不同的含义 。[`cc_library()`](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_library)对于 C++ 库，`linkstatic=True`表示只允许静态链接，因此不会`.so`生成。linkstatic=False 不会阻止创建静态库。该属性旨在控制动态库的创建。如果`linkstatic=False`，则构建工具将创建指向该区域中依赖的共享库的符号链接`*.runfiles`。 |
| `local_defines`            | `List of strings; optional`要添加到编译行的定义列表。受限于[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。每个必须由单个 Bourne shell 标记组成的字符串都被`-D`添加到该目标的编译命令行中，但不添加到它的依赖项中。 |
| `malloc`                   | `Label; optional; default is @bazel_tools//tools/cpp:malloc`覆盖对 malloc 的默认依赖项。默认情况下，C++ 二进制文件链接到`//tools/cpp:malloc`，这是一个空库，因此二进制文件最终使用 libc malloc。此标签必须引用一个`cc_library`. 如果编译是针对非 C++ 规则的，则此选项无效。如果指定，则忽略此属性的值 `linkshared=True`。 |
| `nocopts`                  | `String; optional`从 C++ 编译命令中删除匹配选项。以[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。此属性的值被解释为正则表达式。任何`COPTS`与此正则表达式匹配的预先存在的内容（包括在规则的[copts](https://docs.bazel.build/versions/main/be/c-cpp.html#cc_binary.copts)属性中明确指定的值）都将被删除， `COPTS`以便编译此规则。这个属性应该很少需要。 |
| `stamp`                    | `Integer; optional; default is 0`是否将构建信息编码到二进制文件中。可能的值：`stamp = 1`：始终将构建信息标记到二进制文件中，即使在 [`--nostamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)构建中也是如此。**应该避免此设置**，因为它可能会杀死二进制文件的远程缓存以及依赖它的任何下游操作。`stamp = 0`：始终用常量值替换构建信息。这提供了良好的构建结果缓存。`stamp = -1`：构建信息的嵌入由 [`--[no\]stamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)标志控制。*除非它们的依赖关系发生变化，否则不会*重建标记的二进制文件。 |
| `win_def_file`             | `Label; optional`要传递给链接器的 Windows DEF 文件。仅当 Windows 是目标平台时才应使用此属性。它可用于在链接共享库期间[ 导出符号。](https://msdn.microsoft.com/en-us/library/d91k01sh.aspx) |

## cc_toolchain

```
cc_toolchain(name, all_files, ar_files, as_files, compatible_with, compiler, compiler_files, compiler_files_without_includes, coverage_files, cpu, deprecation, distribs, dwp_files, dynamic_runtime_lib, exec_transition_for_inputs, features, libc_top, licenses, linker_files, module_map, objcopy_files, restricted_to, static_runtime_lib, strip_files, supports_header_parsing, supports_param_files, tags, target_compatible_with, testonly, toolchain_config, toolchain_identifier, visibility)
```

表示 C++ 工具链。

该规则负责：

- 收集运行 C++ 操作所需的所有工件。这是通过诸如`all_files`、`compiler_files`、 `linker_files`或其他以 ) 结尾的属性来完成的`_files`。这些是最常见的文件组，包含所有必需的文件。
- 为 C++ 操作生成正确的命令行。这是使用 `CcToolchainConfigInfo`提供者完成的（详情如下）。

使用`toolchain_config`属性来配置 C++ 工具链。另请参阅此 [页面 ](https://docs.bazel.build/versions/main/cc-toolchain-config-reference.html)以获取详细的 C++ 工具链配置和工具链选择文档。

用于`tags = ["manual"]`防止在调用时不必要地构建和配置工具链`bazel build //...`

### 参数

| 属性                              |                                                              |
| :-------------------------------- | ------------------------------------------------------------ |
| `name`                            | `Name; required`此目标的唯一名称。                           |
| `all_files`                       | `Label; required`所有 cc_toolchain 工件的集合。这些工件将作为输入添加到所有 rules_cc 相关操作（使用以下属性中更精确的工件集的操作除外）。Bazel 假设它`all_files`是所有其他提供工件的属性的超集（例如，linkstamp 编译需要编译和链接文件，所以它需要`all_files`）。这是`cc_toolchain.files`包含的内容，所有 Starlark 规则都使用 C++ 工具链。 |
| `ar_files`                        | `Label; optional`归档操作所需的所有 cc_toolchain 工件的集合。 |
| `as_files`                        | `Label; optional`集合操作所需的所有 cc_toolchain 工件的集合。 |
| `compiler`                        | `String; optional; nonconfigurable`已弃用。改用`toolchain_identifier`属性。[ 在CROSSTOOL 迁移到 Starlark ](https://github.com/bazelbuild/bazel/issues/5380)后它将是一个 noop ，并将被 [#7075](https://github.com/bazelbuild/bazel/issues/7075)删除。设置后，它将用于执行 crosstool_config.toolchain 选择。它将优先于 --cpu Bazel 选项。 |
| `compiler_files`                  | `Label; required`编译操作所需的所有 cc_toolchain 工件的集合。目前仅由 lto_backend 操作使用，常规编译操作使用 all_files ( [#6927](https://github.com/bazelbuild/bazel/issues/6927) )。 |
| `compiler_files_without_includes` | `Label; optional`在支持输入发现的情况下（目前仅限 Google），收集编译操作所需的所有 cc_toolchain 工件。 |
| `coverage_files`                  | `Label; optional`覆盖操作所需的所有 cc_toolchain 工件的集合。如果未指定，则使用 all_files。 |
| `cpu`                             | `String; optional; nonconfigurable`已弃用。请改用 toolchain_identifier 属性。[在CROSSTOOL 迁移到 Starlark ](https://github.com/bazelbuild/bazel/issues/5380)后它将是一个 noop ，并将被 [#7075](https://github.com/bazelbuild/bazel/issues/7075)删除。设置后，它将用于执行 crosstool_config.toolchain 选择。它将优先于 --cpu Bazel 选项。 |
| `dwp_files`                       | `Label; required`dwp 操作所需的所有 cc_toolchain 工件的集合。 |
| `dynamic_runtime_lib`             | `Label; optional`C++ 运行时库的动态库工件（例如 libstdc++.so）。这将在启用“static_link_cpp_runtimes”功能时使用，并且我们正在动态链接依赖项。 |
| `exec_transition_for_inputs`      | `Boolean; optional; default is True`设置为 True 为 exec 平台构建所有文件输入到 cc_toolchain，而不是没有转换（即默认情况下的目标平台）。 |
| `libc_top`                        | `Label; optional`libc 的工件集合作为输入传递给编译/链接操作。 |
| `linker_files`                    | `Label; required`链接操作所需的所有 cc_toolchain 工件的集合。 |
| `module_map`                      | `Label; optional`用于模块化构建的模块映射工件。              |
| `objcopy_files`                   | `Label; required`objcopy 操作所需的所有 cc_toolchain 工件的集合。 |
| `static_runtime_lib`              | `Label; optional`C++ 运行时库的静态库工件（例如 libstdc++.a）。这将在启用“static_link_cpp_runtimes”功能时使用，并且我们正在静态链接依赖项。 |
| `strip_files`                     | `Label; required`剥离操作所需的所有 cc_toolchain 工件的集合。 |
| `supports_header_parsing`         | `Boolean; optional; default is False`当 cc_toolchain 支持标头解析操作时设置为 True。 |
| `supports_param_files`            | `Boolean; optional; default is True`当 cc_toolchain 支持使用参数文件进行链接操作时设置为 True。 |
| `toolchain_config`                | `Label; required`提供 的规则的标签`cc_toolchain_config_info`。 |
| `toolchain_identifier`            | `String; optional; nonconfigurable`用于将此 cc_toolchain 与相应的 crosstool_config.toolchain 匹配的标识符。在问题[#5380](https://github.com/bazelbuild/bazel/issues/5380)得到修复之前，这是`cc_toolchain`与 `CROSSTOOL.toolchain`. 它将被`toolchain_config` 属性 ( [#5380](https://github.com/bazelbuild/bazel/issues/5380) ) 替换。 |

## cc_toolchain_suite

```
cc_toolchain_suite(name, compatible_with, deprecation, distribs, features, licenses, restricted_to, tags, target_compatible_with, testonly, toolchains, visibility)
```

表示 C++ 工具链的集合。

该规则负责：

- 收集所有相关的 C++ 工具链。
- 根据传递给 Bazel 的选项 `--cpu`选择 一个工具链。`--compiler`



另请参阅此 [页面 ](https://docs.bazel.build/versions/main/cc-toolchain-config-reference.html)以获取详细的 C++ 工具链配置和工具链选择文档。

### 参数

| 属性         |                                                              |
| :----------- | ------------------------------------------------------------ |
| `name`       | `Name; required`此目标的唯一名称。                           |
| `toolchains` | `Dictionary mapping strings to labels; required; nonconfigurable`从“<cpu>”或“<cpu>|<compiler>”字符串到`cc_toolchain`标签的映射。"<cpu>" 将在 only`--cpu` 传递给 Bazel 时使用，而 "<cpu>|<compiler>" 将在两者 `--cpu`都`--compiler` 传递给 Bazel 时使用。例子：`          cc_toolchain_suite(            name = "工具链",            工具链 = {              "piii|gcc": ":my_cc_toolchain_for_piii_using_gcc",              "piii": ":my_cc_toolchain_for_piii_using_default_compiler",            },          )          ` |



# Java 规则

## 规则

- [java_binary](https://docs.bazel.build/versions/main/be/java.html#java_binary)
- [java_import](https://docs.bazel.build/versions/main/be/java.html#java_import)
- [java_library](https://docs.bazel.build/versions/main/be/java.html#java_library)
- [java_lite_proto_library](https://docs.bazel.build/versions/main/be/java.html#java_lite_proto_library)
- [java_proto_library](https://docs.bazel.build/versions/main/be/java.html#java_proto_library)
- [java_test](https://docs.bazel.build/versions/main/be/java.html#java_test)
- [java_package_configuration](https://docs.bazel.build/versions/main/be/java.html#java_package_configuration)
- [java_plugin](https://docs.bazel.build/versions/main/be/java.html#java_plugin)
- [java_runtime](https://docs.bazel.build/versions/main/be/java.html#java_runtime)
- [java_toolchain](https://docs.bazel.build/versions/main/be/java.html#java_toolchain)

## java_binary

```
java_binary(name, deps, srcs, data, resources, args, classpath_resources, compatible_with, create_executable, deploy_env, deploy_manifest_lines, deprecation, distribs, env, exec_compatible_with, exec_properties, features, javacopts, jvm_flags, launcher, licenses, main_class, output_licenses, plugins, resource_jars, resource_strip_prefix, restricted_to, runtime_deps, stamp, tags, target_compatible_with, testonly, toolchains, use_launcher, use_testrunner, visibility)
```

构建一个 Java 归档文件（“jar 文件”），以及一个与规则同名的包装器 shell 脚本。包装器 shell 脚本使用一个类路径，其中包括二进制文件所依赖的每个库的 jar 文件等。

包装脚本接受几个独特的标志。`//src/main/java/com/google/devtools/build/lib/bazel/rules/java/java_stub_template.txt` 有关包装器接受的可配置标志和环境变量的列表， 请参阅 。

#### 隐式输出目标

- `name.jar`: 一个 Java 存档，包含与二进制文件的直接依赖关系对应的类文件和其他资源。

- `name-src.jar`：包含源的存档（“source jar”）。

- ```
  name_deploy.jar
  ```

  ：适合部署的 Java 存档（仅在明确要求时构建）。

  为您的规则构建目标会创建一个包含清单的自包含 jar 文件，该清单允许它使用 命令或包装脚本的 选项运行。首选使用包装脚本，因为它还传递[JVM 标志](https://docs.bazel.build/versions/main/be/java.html#java_binary.jvm_flags)和加载本机库的选项。 `<name>_deploy.jar``java -jar``--singlejar``java -jar`

  部署 jar 包含类加载器将找到的所有类，该类加载器从头到尾从二进制文件的包装脚本中搜索类路径。它还包含依赖项所需的本机库。这些会在运行时自动加载到 JVM 中。

  如果您的目标指定了[启动器](https://docs.bazel.build/versions/main/be/java.html#java_binary.launcher) 属性，那么 _deploy.jar 将不是普通的 JAR 文件，而是本机二进制文件。这将包含启动器以及规则的任何本机 (C++) 依赖项，所有这些都链接到静态二进制文件中。实际 jar 文件的字节将附加到该本机二进制文件，创建一个包含可执行文件和 Java 代码的二进制 blob。您可以像执行任何本机二进制文件一样直接执行生成的 jar 文件。

- `name_deploy-src.jar`：包含从目标的传递闭包收集的源的档案。这些将匹配 `deploy.jar`jar 中没有匹配源 jar 的类中的类。

没有;的规则 `deps`中不允许 使用属性 这样的规则需要由 提供 。 `java_binary`[`srcs`](https://docs.bazel.build/versions/main/be/java.html#java_binary.srcs)[`main_class`](https://docs.bazel.build/versions/main/be/java.html#java_binary.main_class)[`runtime_deps`](https://docs.bazel.build/versions/main/be/java.html#java_binary.runtime_deps)

以下代码片段说明了一个常见错误：

```
java_binary(
    name = "DontDoThis",
    srcs = [
        ...,
        "GeneratedJavaFile.java",  # a generated .java file
    ],
    deps = [":generating_rule",],  # rule that generates that file
)
```

改为这样做：

```
java_binary(
    name = "DoThisInstead",
    srcs = [
        ...,
        ":generating_rule",
    ],
)
```

### 参数

| 属性                    |                                                              |
| :---------------------- | ------------------------------------------------------------ |
| `name`                  | `Name; required`此目标的唯一名称。 使用作为应用程序主要入口点的源文件的名称（减去扩展名）是一种很好的做法。例如，如果您的入口点被称为 `Main.java`，那么您的名字可能是`Main`。 |
| `deps`                  | `List of labels; optional`要链接到目标的其他库的列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`deps`的 属性的一般评论。 |
| `srcs`                  | `List of labels; optional`为创建目标而处理的源文件列表。这个属性几乎总是需要的；请参阅下面的例外情况。类型的源文件`.java`被编译。对于生成的 `.java`文件，通常建议将生成规则的名称放在此处，而不是文件本身的名称。这不仅提高了可读性，而且使规则对未来的变化更具弹性：如果生成规则将来生成不同的文件，您只需要修复一个地方：`outs`生成规则的。您不应该在其中列出生成规则，`deps` 因为它是无操作的。类型的源文件`.srcjar`被解包和编译。（如果您需要`.java`使用 genrule 生成一组文件，这很有用。）规则：如果规则（通常是`genrule`或`filegroup`）生成上面列出的任何文件，它们的使用方式与源文件描述的方式相同。这个参数几乎总是需要的，除非一个 [`main_class`](https://docs.bazel.build/versions/main/be/java.html#java_binary.main_class)属性在运行时类路径上指定了一个类或者你指定了`runtime_deps`参数。 |
| `resources`             | `List of labels; optional`要包含在 Java jar 中的数据文件列表。如果指定了资源，它们将与 `.class`编译生成的常用文件一起捆绑在 jar 中。jar 文件中资源的位置由项目结构决定。Bazel 首先查找 Maven 的 [标准目录布局](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html)，（“src”目录后跟“resources”目录孙子）。如果没有找到，Bazel 然后查找名为“java”或“javatests”的最顶层目录（因此，例如，如果资源位于`<workspace root>/x/java/y/java/z`，则资源的路径将为`y/java/z`。这种启发式不能被覆盖。资源可能是源文件或生成的文件。 |
| `classpath_resources`   | `List of labels; optional`*除非没有其他方法，否则不要使用此选项）*必须位于 java 树根目录的资源列表。此属性的唯一目的是支持要求在类路径中准确找到其资源的第三方库`"myconfig.xml"`。由于命名空间冲突的危险，它只允许在二进制文件而不是库上。 |
| `create_executable`     | `Boolean; optional; nonconfigurable; default is True`二进制文件是否可执行。不可执行的二进制文件将传递运行时 Java 依赖项收集到部署 jar 中，但不能直接执行。如果设置了此属性，则不会创建包装脚本。如果设置了`launcher`or`main_class`属性，则将其设置为 0 是错误的。 |
| `deploy_env`            | `List of labels; optional``java_binary`代表此二进制文件部署环境 的其他目标列表。在构建将由另一个加载的插件时设置此属性 `java_binary`。 设置此属性会排除此二进制文件的运行时类路径（和部署 jar）中在此二进制文件和`deploy_env`. |
| `deploy_manifest_lines` | `List of strings; optional`要添加到为目标`META-INF/manifest.mf`生成的文件 的行列表。`*_deploy.jar`此属性的内容不受*“*[制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换的影响。 |
| `javacopts`             | `List of strings; optional`此库的额外编译器选项。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。这些编译器选项在全局编译器选项之后传递给 javac。 |
| `jvm_flags`             | `List of strings; optional`要嵌入到为运行此二进制文件而生成的包装脚本中的标志列表。受限于[$(location)](https://docs.bazel.build/versions/main/be/make-variables.html#location)和 [“Make variable”](https://docs.bazel.build/versions/main/be/make-variables.html)替换，以及 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。Java 二进制文件的包装脚本包含一个 CLASSPATH 定义（用于查找所有相关的 jar）并调用正确的 Java 解释器。包装脚本生成的命令行包括主类的名称，后跟a `"$@"`，因此您可以在类名之后传递其他参数。但是，用于 JVM 解析的参数必须在命令行上的类名*之前指定。*的内容`jvm_flags`在列出类名之前添加到包装脚本中。请注意，此属性对 输出*没有影响。*`*_deploy.jar` |
| `launcher`              | `Label; optional`指定将用于运行 Java 程序而不是`bin/java`JDK 中包含的普通程序的二进制文件。目标必须是`cc_binary`. 任何`cc_binary`实现 [Java 调用 API](http://docs.oracle.com/javase/7/docs/technotes/guides/jni/spec/invocation.html)的都可以指定为此属性的值。默认情况下，Bazel 将使用普通的 JDK 启动器（bin/java 或 java.exe）。相关的Bazel 标志仅影响*未*指定属性的[` --java_launcher`](https://docs.bazel.build/versions/main/user-manual.html#flag--java_launcher)那些 `java_binary`和`java_test`目标 。`launcher`请注意，您的本机（C++、SWIG、JNI）依赖项的构建方式会有所不同，具体取决于您使用的是 JDK 启动器还是其他启动器：如果您使用的是普通的 JDK 启动器（默认），本机依赖项将构建为一个名为 的共享库`{name}_nativedeps.so`，这里 java_binary 规则`{name}`的属性在哪里。在此配置中，链接器*不会*`name`删除未使用的代码。如果您使用任何其他启动器，本机 (C++) 依赖项将静态链接到名为 的二进制文件`{name}_nativedeps`中，其中`{name}` 是`name`此 java_binary 规则的属性。在这种情况下，链接器将从生成的二进制文件中删除它认为未使用的任何代码，这意味着只能通过 JNI 访问的任何 C++ 代码可能不会被链接，除非该`cc_library`目标指定`alwayslink = 1`.使用默认 JDK 启动器以外的任何启动器时，`*_deploy.jar`输出的格式会发生变化。有关详细信息，请参阅主要的 [java_binary](https://docs.bazel.build/versions/main/be/java.html#java_binary)文档。 |
| `main_class`            | `String; optional``main()`具有用作入口点的方法 的类的名称。如果规则使用此选项，则不需要`srcs=[...]`列表。因此，使用此属性，可以从已经包含一个或多个`main()`方法的 Java 库中生成可执行文件。该属性的值是类名，而不是源文件。该类必须在运行时可用：它可以通过此规则编译（from `srcs`）或由直接或传递依赖项（通过`runtime_deps`or `deps`）提供。如果该类不可用，则二进制文件将在运行时失败；没有构建时检查。 |
| `plugins`               | `List of labels; optional`在编译时运行的 Java 编译器插件。每当`java_plugin`构建此规则时，此属性中指定的每个都将运行。库也可以从使用 `exported_plugins`. 插件生成的资源将包含在此规则的生成 jar 中。 |
| `resource_jars`         | `List of labels; optional`一组包含 Java 资源的档案。如果指定，这些 jar 的内容将合并到输出 jar 中。 |
| `resource_strip_prefix` | `String; optional`从 Java 资源中剥离的路径前缀。如果指定，则从`resources` 属性中的每个文件中删除此路径前缀。资源文件不在此目录下是错误的。如果不指定（默认），则资源文件的路径根据与源文件的Java包相同的逻辑来确定。例如，源文件 `stuff/java/foo/bar/a.txt`位于`foo/bar/a.txt`. |
| `runtime_deps`          | `List of labels; optional`仅在运行时可用于最终二进制文件或测试的库。像普通`deps`的，这些将出现在运行时类路径中，但与它们不同的是，它们不会出现在编译时类路径中。此处应列出仅在运行时需要的依赖项。依赖分析工具应该忽略同时出现在 `runtime_deps`和中的目标`deps`。 |
| `stamp`                 | `Integer; optional; default is -1`是否将构建信息编码到二进制文件中。可能的值：`stamp = 1`：始终将构建信息标记到二进制文件中，即使在 [`--nostamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)构建中也是如此。**应该避免此设置**，因为它可能会杀死二进制文件的远程缓存以及依赖它的任何下游操作。`stamp = 0`：始终用常量值替换构建信息。这提供了良好的构建结果缓存。`stamp = -1`：构建信息的嵌入由 [`--[no\]stamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)标志控制。*除非它们的依赖关系发生变化，否则不会*重建标记的二进制文件。 |
| `use_launcher`          | `Boolean; optional; default is True`二进制文件是否应该使用自定义启动器。如果此属性设置为 false，则此目标的 [启动器](https://docs.bazel.build/versions/main/be/java.html#java_binary.launcher)属性和相关 [`--java_launcher`](https://docs.bazel.build/versions/main/user-manual.html#flag--java_launcher)标志将被忽略。 |
| `use_testrunner`        | `Boolean; optional; default is False`使用测试运行器（默认 `com.google.testing.junit.runner.BazelTestRunner`）类作为 Java 程序的主要入口点，并将测试类作为`bazel.test_suite` 系统属性的值提供给测试运行器。您可以使用它来覆盖默认行为，即将测试运行器用于 `java_test`规则，而不是将其用于`java_binary`规则。您不太可能想要这样做。一种用途是用于`AllTest` 由另一个规则调用的规则（例如，在运行测试之前设置数据库）。该`AllTest` 规则必须声明为`java_binary`，但仍应使用测试运行器作为其主要入口点。测试运行器类的名称可以用`main_class`属性覆盖。 |

## java_import

```
java_import(name, deps, data, compatible_with, constraints, deprecation, distribs, exec_compatible_with, exec_properties, exports, features, jars, licenses, neverlink, proguard_specs, restricted_to, runtime_deps, srcjar, tags, target_compatible_with, testonly, visibility)
```

此规则允许使用预编译`.jar`文件作为库`java_library`和 `java_binary`规则。

#### 例子

```
     java_import(
        name = "maven_model",
        jars = [
            "maven_model/maven-aether-provider-3.2.3.jar",
            "maven_model/maven-model-3.2.3.jar",
            "maven_model/maven-model-builder-3.2.3.jar",
        ],
    )
```

### 参数

| 属性             |                                                              |
| :--------------- | ------------------------------------------------------------ |
| `name`           | `Name; required`此目标的唯一名称。                           |
| `deps`           | `List of labels; optional`要链接到目标的其他库的列表。请参阅[java_library.deps](https://docs.bazel.build/versions/main/be/java.html#java_library.deps)。 |
| `constraints`    | `List of strings; optional; nonconfigurable`将此规则作为 Java 库施加的额外限制。 |
| `exports`        | `List of labels; optional`向此规则的用户提供的目标。请参阅[java_library.exports](https://docs.bazel.build/versions/main/be/java.html#java_library.exports)。 |
| `jars`           | `List of labels; required`提供给依赖此目标的 Java 目标的 JAR 文件列表。 |
| `neverlink`      | `Boolean; optional; default is False`仅将此库用于编译而不是在运行时。如果库将在执行期间由运行时环境提供，则很有用。像这样的库的例子是 IDE 插件的 IDE API 或`tools.jar`在标准 JDK 上运行的任何东西。 |
| `proguard_specs` | `List of labels; optional`用作 Proguard 规范的文件。这些将描述 Proguard 使用的规范集。如果指定，它们将`android_binary`根据此库添加到任何目标。这里包含的文件必须只有幂等规则，即-dontnote、-dontwarn、assumenosideeffects，以及以-keep开头的规则。其他选项只能出现在 `android_binary`的 proguard_specs 中，以确保非重言式合并。 |
| `runtime_deps`   | `List of labels; optional`仅在运行时可用于最终二进制文件或测试的库。请参阅[java_library.runtime_deps](https://docs.bazel.build/versions/main/be/java.html#java_library.runtime_deps)。 |
| `srcjar`         | `Label; optional`一个 JAR 文件，其中包含已编译 JAR 文件的源代码。 |

## java_library

```
java_library(name, deps, srcs, data, resources, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, exported_plugins, exports, features, javacopts, licenses, neverlink, plugins, proguard_specs, resource_jars, resource_strip_prefix, restricted_to, runtime_deps, tags, target_compatible_with, testonly, visibility)
```

此规则将源代码编译并链接到`.jar`文件中。

#### 隐式输出目标

- `libname.jar`: 包含类文件的 Java 存档。
- `libname-src.jar`：包含源的存档（“source jar”）。

### 参数

| 属性                    |                                                              |
| :---------------------- | ------------------------------------------------------------ |
| `name`                  | `Name; required`此目标的唯一名称。                           |
| `deps`                  | `List of labels; optional`要链接到此库的库列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`deps`的 属性的一般评论。`java_library`中列出的规则 构建的 jar`deps`将位于此规则的编译时类路径中。此外，它们的传递闭包 `deps`,`runtime_deps`并将`exports`位于运行时类路径上。相比之下，`data`属性中的目标包含在运行文件中，但既不在编译时也不在运行时类路径中。 |
| `srcs`                  | `List of labels; optional`为创建目标而处理的源文件列表。这个属性几乎总是需要的；请参阅下面的例外情况。类型的源文件`.java`被编译。对于生成的 `.java`文件，通常建议将生成规则的名称放在此处，而不是文件本身的名称。这不仅提高了可读性，而且使规则对未来的变化更具弹性：如果生成规则将来生成不同的文件，您只需要修复一个地方：`outs`生成规则的。您不应该在其中列出生成规则，`deps` 因为它是无操作的。类型的源文件`.srcjar`被解包和编译。（如果您需要`.java`使用 genrule 生成一组文件，这很有用。）规则：如果规则（通常是`genrule`或`filegroup`）生成上面列出的任何文件，它们的使用方式与源文件描述的方式相同。这个参数几乎总是需要的，除非一个 [`main_class`](https://docs.bazel.build/versions/main/be/java.html#java_binary.main_class)属性在运行时类路径上指定了一个类或者你指定了`runtime_deps`参数。 |
| `data`                  | `List of labels; optional`此库在运行时所需的文件列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`data`的 属性的一般评论。在构建 时`java_library`，Bazel 不会将这些文件放在任何地方；如果 `data`文件是生成的文件，那么 Bazel 会生成它们。在构建依赖于此`java_library`Bazel 的测试时，会将文件复制或链接到 `data`运行文件区域。 |
| `resources`             | `List of labels; optional`要包含在 Java jar 中的数据文件列表。如果指定了资源，它们将与 `.class`编译生成的常用文件一起捆绑在 jar 中。jar 文件中资源的位置由项目结构决定。Bazel 首先查找 Maven 的 [标准目录布局](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html)，（“src”目录后跟“resources”目录孙子）。如果没有找到，Bazel 然后查找名为“java”或“javatests”的最顶层目录（因此，例如，如果资源位于`<workspace root>/x/java/y/java/z`，则资源的路径将为`y/java/z`。这种启发式不能被覆盖。资源可能是源文件或生成的文件。 |
| `exported_plugins`      | `List of labels; optional``java_plugin`要导出到直接依赖于该库的库 的 s 列表（例如注释处理器）。指定的`java_plugin`s 列表将应用于直接依赖于该库的任何库，就好像该库已在`plugins`. |
| `exports`               | `List of labels; optional`导出的库。在此处列出规则将使它们可用于父规则，就好像父规则明确依赖这些规则一样。这不适用于常规（非导出）`deps`。总结：规则*X*可以访问*Y*中的代码，如果它们之间存在以一条`deps`边开始，后跟零个或多个 `exports`边的依赖路径。让我们看一些例子来说明这一点。假设*A*依赖于*B*并且*B*依赖于*C*。在这种情况下，C 是 A 的*传递*依赖，因此更改 C 的源并重新构建 A 将正确地重新构建所有内容。但是，A 将无法在 C 中使用类。为此，A 必须在其 中声明 C `deps`，或者 B 可以通过在其 (B's) 中声明 C 来使 A（以及可能依赖于 A 的任何事物）更容易`exports` 属性。导出库的关闭可用于所有直接父规则。举一个稍微不同的例子：A 依赖于 B，B 依赖于 C 和 D，也导出 C 但不导出 D。现在 A 可以访问 C 但不能访问 D。现在，如果 C 和 D 导出了一些库，C' 和D' 分别表示 A 只能访问 C' 而不能访问 D'。重要提示：导出的规则不是常规依赖项。继续前面的例子，如果 B 导出 C 并且还想使用 C，它也必须将它列在它自己的 `deps`. |
| `javacopts`             | `List of strings; optional`此库的额外编译器选项。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。这些编译器选项在全局编译器选项之后传递给 javac。 |
| `neverlink`             | `Boolean; optional; default is False`这个库是否应该只用于编译而不是在运行时。如果库将在执行期间由运行时环境提供，则很有用。此类库的示例是用于 IDE 插件或`tools.jar`在标准 JDK 上运行的任何东西的 IDE API。请注意，`neverlink = 1`这并不妨碍编译器将此库中的材料内联到依赖它的编译目标中，这是 Java 语言规范所允许的（例如，原始类型的`static final`常量`String` 或原始类型的常量）。因此，首选用例是运行时库与编译库相同时。如果运行时库与编译库不同，那么您必须确保它仅在 JLS 禁止编译器内联的地方有所不同（并且必须适用于 JLS 的所有未来版本）。 |
| `plugins`               | `List of labels; optional`在编译时运行的 Java 编译器插件。每当`java_plugin`构建此规则时，此属性中指定的每个都将运行。库也可以从使用 `exported_plugins`. 插件生成的资源将包含在此规则的生成 jar 中。 |
| `proguard_specs`        | `List of labels; optional`用作 Proguard 规范的文件。这些将描述 Proguard 使用的规范集。如果指定，它们将`android_binary`根据此库添加到任何目标。这里包含的文件必须只有幂等规则，即-dontnote、-dontwarn、assumenosideeffects，以及以-keep开头的规则。其他选项只能出现在 `android_binary`的 proguard_specs 中，以确保非重言式合并。 |
| `resource_jars`         | `List of labels; optional`一组包含 Java 资源的档案。如果指定，这些 jar 的内容将合并到输出 jar 中。 |
| `resource_strip_prefix` | `String; optional`从 Java 资源中剥离的路径前缀。如果指定，则从`resources` 属性中的每个文件中删除此路径前缀。资源文件不在此目录下是错误的。如果不指定（默认），则资源文件的路径根据与源文件的Java包相同的逻辑来确定。例如，源文件 `stuff/java/foo/bar/a.txt`位于`foo/bar/a.txt`. |
| `runtime_deps`          | `List of labels; optional`仅在运行时可用于最终二进制文件或测试的库。像普通`deps`的，这些将出现在运行时类路径中，但与它们不同的是，它们不会出现在编译时类路径中。此处应列出仅在运行时需要的依赖项。依赖分析工具应该忽略同时出现在 `runtime_deps`和中的目标`deps`。 |

## java_lite_proto_library

```
java_lite_proto_library(name, deps, data, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, features, licenses, restricted_to, tags, target_compatible_with, testonly, visibility)
```

`java_lite_proto_library``.proto`从文件 生成 Java 代码。

`deps`必须指向[`proto_library `](https://docs.bazel.build/versions/main/be/protocol-buffer.html#proto_library)规则。

例子：

```
java_library(
    name = "lib",
    deps = [":foo"],
)

java_lite_proto_library(
    name = "foo",
    deps = [":bar"],
)

proto_library(
    name = "bar",
)
```

### 参数

| 属性   |                                                              |
| :----- | ------------------------------------------------------------ |
| `name` | `Name; required`此目标的唯一名称。                           |
| `deps` | `List of labels; optional`[`proto_library`](https://docs.bazel.build/versions/main/be/protocol-buffer.html#proto_library) 为其生成 Java 代码 的规则列表。 |

## java_proto_library

```
java_proto_library(name, deps, data, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, features, licenses, restricted_to, tags, target_compatible_with, testonly, visibility)
```

`java_proto_library``.proto`从文件 生成 Java 代码。

`deps`必须指向[`proto_library `](https://docs.bazel.build/versions/main/be/protocol-buffer.html#proto_library)规则。

例子：

```
java_library(
    name = "lib",
    deps = [":foo_java_proto"],
)

java_proto_library(
    name = "foo_java_proto",
    deps = [":foo_proto"],
)

proto_library(
    name = "foo_proto",
)
```

### 参数

| 属性   |                                                              |
| :----- | ------------------------------------------------------------ |
| `name` | `Name; required`此目标的唯一名称。                           |
| `deps` | `List of labels; optional`[`proto_library`](https://docs.bazel.build/versions/main/be/protocol-buffer.html#proto_library) 为其生成 Java 代码 的规则列表。 |

## java_test

```
java_test(name, deps, srcs, data, resources, args, classpath_resources, compatible_with, create_executable, deploy_manifest_lines, deprecation, distribs, env, env_inherit, exec_compatible_with, exec_properties, features, flaky, javacopts, jvm_flags, launcher, licenses, local, main_class, plugins, resource_jars, resource_strip_prefix, restricted_to, runtime_deps, shard_count, size, stamp, tags, target_compatible_with, test_class, testonly, timeout, toolchains, use_launcher, use_testrunner, visibility)
```

`java_test()`规则编译 Java 测试 。测试是围绕测试代码的二进制包装器。调用测试运行程序的 main 方法，而不是编译的主类。

#### 隐式输出目标

- `name.jar`: 一个 Java 档案。
- `name_deploy.jar`：适合部署的 Java 存档。（仅在明确请求时构建。）有关 更多详细信息，请参阅[java_binary](https://docs.bazel.build/versions/main/be/java.html#java_binary)`name_deploy.jar`输出 的描述。

请参阅有关[java_binary()](https://docs.bazel.build/versions/main/be/java.html#java_binary_args)参数的部分。此规则还支持所有[测试规则 (*_test) 共有的所有属性](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes-tests)。

#### 例子

```
java_library(
    name = "tests",
    srcs = glob(["*.java"]),
    deps = [
        "//java/com/foo/base:testResources",
        "//java/com/foo/testing/util",
    ],
)

java_test(
    name = "AllTests",
    size = "small",
    runtime_deps = [
        ":tests",
        "//util/mysql",
    ],
)
```

### 参数

| 属性                    |                                                              |
| :---------------------- | ------------------------------------------------------------ |
| `name`                  | `Name; required`此目标的唯一名称。                           |
| `deps`                  | `List of labels; optional`要链接到目标的其他库的列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`deps`的 属性的一般评论。 |
| `srcs`                  | `List of labels; optional`为创建目标而处理的源文件列表。这个属性几乎总是需要的；请参阅下面的例外情况。类型的源文件`.java`被编译。对于生成的 `.java`文件，通常建议将生成规则的名称放在此处，而不是文件本身的名称。这不仅提高了可读性，而且使规则对未来的变化更具弹性：如果生成规则将来生成不同的文件，您只需要修复一个地方：`outs`生成规则的。您不应该在其中列出生成规则，`deps` 因为它是无操作的。类型的源文件`.srcjar`被解包和编译。（如果您需要`.java`使用 genrule 生成一组文件，这很有用。）规则：如果规则（通常是`genrule`或`filegroup`）生成上面列出的任何文件，它们的使用方式与源文件描述的方式相同。这个参数几乎总是需要的，除非一个 [`main_class`](https://docs.bazel.build/versions/main/be/java.html#java_binary.main_class)属性在运行时类路径上指定了一个类或者你指定了`runtime_deps`参数。 |
| `resources`             | `List of labels; optional`要包含在 Java jar 中的数据文件列表。如果指定了资源，它们将与 `.class`编译生成的常用文件一起捆绑在 jar 中。jar 文件中资源的位置由项目结构决定。Bazel 首先查找 Maven 的 [标准目录布局](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html)，（“src”目录后跟“resources”目录孙子）。如果没有找到，Bazel 然后查找名为“java”或“javatests”的最顶层目录（因此，例如，如果资源位于`<workspace root>/x/java/y/java/z`，则资源的路径将为`y/java/z`。这种启发式不能被覆盖。资源可能是源文件或生成的文件。 |
| `classpath_resources`   | `List of labels; optional`*除非没有其他方法，否则不要使用此选项）*必须位于 java 树根目录的资源列表。此属性的唯一目的是支持要求在类路径中准确找到其资源的第三方库`"myconfig.xml"`。由于命名空间冲突的危险，它只允许在二进制文件而不是库上。 |
| `create_executable`     | `Boolean; optional; nonconfigurable; default is True`二进制文件是否可执行。不可执行的二进制文件将传递运行时 Java 依赖项收集到部署 jar 中，但不能直接执行。如果设置了此属性，则不会创建包装脚本。如果设置了`launcher`or`main_class`属性，则将其设置为 0 是错误的。 |
| `deploy_manifest_lines` | `List of strings; optional`要添加到为目标`META-INF/manifest.mf`生成的文件 的行列表。`*_deploy.jar`此属性的内容不受*“*[制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换的影响。 |
| `javacopts`             | `List of strings; optional`此库的额外编译器选项。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。这些编译器选项在全局编译器选项之后传递给 javac。 |
| `jvm_flags`             | `List of strings; optional`要嵌入到为运行此二进制文件而生成的包装脚本中的标志列表。受限于[$(location)](https://docs.bazel.build/versions/main/be/make-variables.html#location)和 [“Make variable”](https://docs.bazel.build/versions/main/be/make-variables.html)替换，以及 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。Java 二进制文件的包装脚本包含一个 CLASSPATH 定义（用于查找所有相关的 jar）并调用正确的 Java 解释器。包装脚本生成的命令行包括主类的名称，后跟a `"$@"`，因此您可以在类名之后传递其他参数。但是，用于 JVM 解析的参数必须在命令行上的类名*之前指定。*的内容`jvm_flags`在列出类名之前添加到包装脚本中。请注意，此属性对 输出*没有影响。*`*_deploy.jar` |
| `launcher`              | `Label; optional`指定将用于运行 Java 程序而不是`bin/java`JDK 中包含的普通程序的二进制文件。目标必须是`cc_binary`. 任何`cc_binary`实现 [Java 调用 API](http://docs.oracle.com/javase/7/docs/technotes/guides/jni/spec/invocation.html)的都可以指定为此属性的值。默认情况下，Bazel 将使用普通的 JDK 启动器（bin/java 或 java.exe）。相关的Bazel 标志仅影响*未*指定属性的[` --java_launcher`](https://docs.bazel.build/versions/main/user-manual.html#flag--java_launcher)那些 `java_binary`和`java_test`目标 。`launcher`请注意，您的本机（C++、SWIG、JNI）依赖项的构建方式会有所不同，具体取决于您使用的是 JDK 启动器还是其他启动器：如果您使用的是普通的 JDK 启动器（默认），本机依赖项将构建为一个名为 的共享库`{name}_nativedeps.so`，这里 java_binary 规则`{name}`的属性在哪里。在此配置中，链接器*不会*`name`删除未使用的代码。如果您使用任何其他启动器，本机 (C++) 依赖项将静态链接到名为 的二进制文件`{name}_nativedeps`中，其中`{name}` 是`name`此 java_binary 规则的属性。在这种情况下，链接器将从生成的二进制文件中删除它认为未使用的任何代码，这意味着只能通过 JNI 访问的任何 C++ 代码可能不会被链接，除非该`cc_library`目标指定`alwayslink = 1`.使用默认 JDK 启动器以外的任何启动器时，`*_deploy.jar`输出的格式会发生变化。有关详细信息，请参阅主要的 [java_binary](https://docs.bazel.build/versions/main/be/java.html#java_binary)文档。 |
| `main_class`            | `String; optional``main()`具有用作入口点的方法 的类的名称。如果规则使用此选项，则不需要`srcs=[...]`列表。因此，使用此属性，可以从已经包含一个或多个`main()`方法的 Java 库中生成可执行文件。该属性的值是类名，而不是源文件。该类必须在运行时可用：它可以通过此规则编译（from `srcs`）或由直接或传递依赖项（通过`runtime_deps`or `deps`）提供。如果该类不可用，则二进制文件将在运行时失败；没有构建时检查。 |
| `plugins`               | `List of labels; optional`在编译时运行的 Java 编译器插件。每当`java_plugin`构建此规则时，此属性中指定的每个都将运行。库也可以从使用 `exported_plugins`. 插件生成的资源将包含在此规则的生成 jar 中。 |
| `resource_jars`         | `List of labels; optional`一组包含 Java 资源的档案。如果指定，这些 jar 的内容将合并到输出 jar 中。 |
| `resource_strip_prefix` | `String; optional`从 Java 资源中剥离的路径前缀。如果指定，则从`resources` 属性中的每个文件中删除此路径前缀。资源文件不在此目录下是错误的。如果不指定（默认），则资源文件的路径根据与源文件的Java包相同的逻辑来确定。例如，源文件 `stuff/java/foo/bar/a.txt`位于`foo/bar/a.txt`. |
| `runtime_deps`          | `List of labels; optional`仅在运行时可用于最终二进制文件或测试的库。像普通`deps`的，这些将出现在运行时类路径中，但与它们不同的是，它们不会出现在编译时类路径中。此处应列出仅在运行时需要的依赖项。依赖分析工具应该忽略同时出现在 `runtime_deps`和中的目标`deps`。 |
| `stamp`                 | `Integer; optional; default is 0`是否将构建信息编码到二进制文件中。可能的值：`stamp = 1`：始终将构建信息标记到二进制文件中，即使在 [`--nostamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)构建中也是如此。**应该避免此设置**，因为它可能会杀死二进制文件的远程缓存以及依赖它的任何下游操作。`stamp = 0`：始终用常量值替换构建信息。这提供了良好的构建结果缓存。`stamp = -1`：构建信息的嵌入由 [`--[no\]stamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)标志控制。*除非它们的依赖关系发生变化，否则不会*重建标记的二进制文件。 |
| `test_class`            | `String; optional`要由测试运行程序加载的 Java 类。 默认情况下，如果未定义此参数，则使用传统模式并使用测试参数。将`--nolegacy_bazel_java_test`标志设置为不回退第一个参数。此属性指定此测试要运行的 Java 类的名称。很少需要设置它。如果省略此参数，则将使用目标`name`及其源根相对路径进行推断。如果测试位于已知源根目录之外，如果`test_class` 未设置，Bazel 将报告错误。对于 JUnit3，测试类需要是 的子类， `junit.framework.TestCase`或者它需要有一个返回 a （或 的子类）的公共静态`suite()`方法 。对于 JUnit4，该类需要使用 . `junit.framework.Test``Test``org.junit.runner.RunWith`此属性允许多个`java_test`规则共享相同的`Test` ( `TestCase`, `TestSuite`, ...)。通常将附加信息传递给它（例如 via `jvm_flags=['-Dkey=value']`），以便它的行为在每种情况下都不同，例如运行不同的测试子集。此属性还允许在`javatests`树之外使用 Java 测试。 |
| `use_launcher`          | `Boolean; optional; default is True`二进制文件是否应该使用自定义启动器。如果此属性设置为 false，则此目标的 [启动器](https://docs.bazel.build/versions/main/be/java.html#java_binary.launcher)属性和相关 [`--java_launcher`](https://docs.bazel.build/versions/main/user-manual.html#flag--java_launcher)标志将被忽略。 |
| `use_testrunner`        | `Boolean; optional; default is True`使用测试运行器（默认 `com.google.testing.junit.runner.BazelTestRunner`）类作为 Java 程序的主要入口点，并将测试类作为`bazel.test_suite` 系统属性的值提供给测试运行器。您可以使用它来覆盖默认行为，即将测试运行器用于 `java_test`规则，而不是将其用于`java_binary`规则。您不太可能想要这样做。一种用途是用于`AllTest` 由另一个规则调用的规则（例如，在运行测试之前设置数据库）。该`AllTest` 规则必须声明为`java_binary`，但仍应使用测试运行器作为其主要入口点。测试运行器类的名称可以用`main_class`属性覆盖。 |

## java_package_configuration

```
java_package_configuration(name, data, compatible_with, deprecation, distribs, features, javacopts, licenses, packages, restricted_to, tags, target_compatible_with, testonly, visibility)
```

应用于一组包的配置。可以将配置添加到 `java_toolchain.javacopts`s.

#### 例子：

```
java_package_configuration(
    name = "my_configuration",
    packages = [":my_packages"],
    javacopts = ["-Werror"],
)

package_group(
    name = "my_packages",
    packages = [
        "//com/my/project/...",
        "-//com/my/project/testing/...",
    ],
)

java_toolchain(
    ...,
    package_configuration = [
        ":my_configuration",
    ]
)
```

### 参数

| 属性        |                                                              |
| :---------- | ------------------------------------------------------------ |
| `name`      | `Name; required`此目标的唯一名称。                           |
| `data`      | `List of labels; optional`此配置在运行时所需的文件列表。     |
| `javacopts` | `List of strings; optional`Java 编译器标志。                 |
| `packages`  | `List of labels; optional``package_group`配置应应用于 的 s 集。 |

## java_plugin

```
java_plugin(name, deps, srcs, data, resources, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, features, generates_api, javacopts, licenses, neverlink, output_licenses, plugins, processor_class, proguard_specs, resource_jars, resource_strip_prefix, restricted_to, tags, target_compatible_with, testonly, visibility)
```

`java_plugin`为 Bazel 运行的 Java 编译器定义插件。目前，唯一支持的插件类型是注释处理器。`java_library`或 规则可以通过 属性`java_binary`依赖它们来运行插件。`plugins`A`java_library`还可以自动将插件导出到直接依赖它的库，使用 `exported_plugins`.

#### 隐式输出目标

- `libname.jar`: 一个 Java 档案。

参数与 相同[`java_library`](https://docs.bazel.build/versions/main/be/java.html#java_library)，只是添加了`processor_class`参数。

### 参数

| 属性                    |                                                              |
| :---------------------- | ------------------------------------------------------------ |
| `name`                  | `Name; required`此目标的唯一名称。                           |
| `deps`                  | `List of labels; optional`要链接到此库的库列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`deps`的 属性的一般评论。`java_library`中列出的规则 构建的 jar`deps`将位于此规则的编译时类路径中。此外，它们的传递闭包 `deps`,`runtime_deps`并将`exports`位于运行时类路径上。相比之下，`data`属性中的目标包含在运行文件中，但既不在编译时也不在运行时类路径中。 |
| `srcs`                  | `List of labels; optional`为创建目标而处理的源文件列表。这个属性几乎总是需要的；请参阅下面的例外情况。类型的源文件`.java`被编译。对于生成的 `.java`文件，通常建议将生成规则的名称放在此处，而不是文件本身的名称。这不仅提高了可读性，而且使规则对未来的变化更具弹性：如果生成规则将来生成不同的文件，您只需要修复一个地方：`outs`生成规则的。您不应该在其中列出生成规则，`deps` 因为它是无操作的。类型的源文件`.srcjar`被解包和编译。（如果您需要`.java`使用 genrule 生成一组文件，这很有用。）规则：如果规则（通常是`genrule`或`filegroup`）生成上面列出的任何文件，它们的使用方式与源文件描述的方式相同。这个参数几乎总是需要的，除非一个 [`main_class`](https://docs.bazel.build/versions/main/be/java.html#java_binary.main_class)属性在运行时类路径上指定了一个类或者你指定了`runtime_deps`参数。 |
| `data`                  | `List of labels; optional`此库在运行时所需的文件列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`data`的 属性的一般评论。在构建 时`java_library`，Bazel 不会将这些文件放在任何地方；如果 `data`文件是生成的文件，那么 Bazel 会生成它们。在构建依赖于此`java_library`Bazel 的测试时，会将文件复制或链接到 `data`运行文件区域。 |
| `resources`             | `List of labels; optional`要包含在 Java jar 中的数据文件列表。如果指定了资源，它们将与 `.class`编译生成的常用文件一起捆绑在 jar 中。jar 文件中资源的位置由项目结构决定。Bazel 首先查找 Maven 的 [标准目录布局](https://maven.apache.org/guides/introduction/introduction-to-the-standard-directory-layout.html)，（“src”目录后跟“resources”目录孙子）。如果没有找到，Bazel 然后查找名为“java”或“javatests”的最顶层目录（因此，例如，如果资源位于`<workspace root>/x/java/y/java/z`，则资源的路径将为`y/java/z`。这种启发式不能被覆盖。资源可能是源文件或生成的文件。 |
| `generates_api`         | `Boolean; optional; default is False`此属性标记生成 API 代码的注释处理器。如果规则使用生成 API 的注释处理器，则依赖于它的其他规则只有在它们的编译操作安排在生成规则之后才能引用生成的代码。此属性指示 Bazel 在启用 --java_header_compilation 时引入调度约束。*警告：此属性会影响构建性能，仅在必要时使用。* |
| `javacopts`             | `List of strings; optional`此库的额外编译器选项。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。这些编译器选项在全局编译器选项之后传递给 javac。 |
| `neverlink`             | `Boolean; optional; default is False`这个库是否应该只用于编译而不是在运行时。如果库将在执行期间由运行时环境提供，则很有用。此类库的示例是用于 IDE 插件或`tools.jar`在标准 JDK 上运行的任何东西的 IDE API。请注意，`neverlink = 1`这并不妨碍编译器将此库中的材料内联到依赖它的编译目标中，这是 Java 语言规范所允许的（例如，原始类型的`static final`常量`String` 或原始类型的常量）。因此，首选用例是运行时库与编译库相同时。如果运行时库与编译库不同，那么您必须确保它仅在 JLS 禁止编译器内联的地方有所不同（并且必须适用于 JLS 的所有未来版本）。 |
| `output_licenses`       | `Licence type; optional`看[`common attributes`](https://docs.bazel.build/versions/main/be/common-definitions.html#binary.output_licenses) |
| `plugins`               | `List of labels; optional`在编译时运行的 Java 编译器插件。每当`java_plugin`构建此规则时，此属性中指定的每个都将运行。库也可以从使用 `exported_plugins`. 插件生成的资源将包含在此规则的生成 jar 中。 |
| `processor_class`       | `String; optional`处理器类是类的完全限定类型，Java 编译器应将其用作注释处理器的入口点。如果未指定，则此规则不会为 Java 编译器的注释处理提供注释处理器，但其运行时类路径仍将包含在编译器的注释处理器路径中。（这主要供 [容易出错的插件使用，这些插件是使用](https://errorprone.info/docs/plugins)[ java.util.ServiceLoader](https://docs.oracle.com/javase/8/docs/api/java/util/ServiceLoader.html)从注释处理器路径加载的 。） |
| `proguard_specs`        | `List of labels; optional`用作 Proguard 规范的文件。这些将描述 Proguard 使用的规范集。如果指定，它们将`android_binary`根据此库添加到任何目标。这里包含的文件必须只有幂等规则，即-dontnote、-dontwarn、assumenosideeffects，以及以-keep开头的规则。其他选项只能出现在 `android_binary`的 proguard_specs 中，以确保非重言式合并。 |
| `resource_jars`         | `List of labels; optional`一组包含 Java 资源的档案。如果指定，这些 jar 的内容将合并到输出 jar 中。 |
| `resource_strip_prefix` | `String; optional`从 Java 资源中剥离的路径前缀。如果指定，则从`resources` 属性中的每个文件中删除此路径前缀。资源文件不在此目录下是错误的。如果不指定（默认），则资源文件的路径根据与源文件的Java包相同的逻辑来确定。例如，源文件 `stuff/java/foo/bar/a.txt`位于`foo/bar/a.txt`. |

## java_runtime

```
java_runtime(name, srcs, compatible_with, deprecation, distribs, features, java, java_home, licenses, restricted_to, tags, target_compatible_with, testonly, visibility)
```

指定 Java 运行时的配置。

#### 例子：

```
java_runtime(
    name = "jdk-9-ea+153",
    srcs = glob(["jdk9-ea+153/**"]),
    java_home = "jdk9-ea+153",
)
```

### 论据

| 属性        |                                                              |
| :---------- | ------------------------------------------------------------ |
| `name`      | `Name; required`此目标的唯一名称。                           |
| `srcs`      | `List of labels; optional`运行时中的所有文件。               |
| `java`      | `Label; optional`java 可执行文件的路径。                     |
| `java_home` | `String; optional`运行时根目录的路径。以[“Make”变量](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。如果此路径是绝对路径，则该规则表示具有已知路径的非封闭 Java 运行时。在这种情况下，`srcs`and`java`属性必须为空。 |

## java_toolchain

```
java_toolchain(name, android_lint_data, android_lint_jvm_opts, android_lint_opts, android_lint_package_configuration, android_lint_runner, bootclasspath, compatible_with, deprecation, distribs, features, forcibly_disable_header_compilation, genclass, header_compiler, header_compiler_direct, ijar, jacocorunner, java_runtime, javabuilder, javabuilder_data, javabuilder_jvm_opts, javac_supports_multiplex_workers, javac_supports_workers, javacopts, jvm_opts, licenses, oneversion, oneversion_whitelist, package_configuration, proguard_allowlister, resourcejar, restricted_to, singlejar, source_version, tags, target_compatible_with, target_version, testonly, timezone_data, tools, turbine_data, turbine_jvm_opts, visibility, xlint)
```

指定 Java 编译器的配置。可以通过 --java_toolchain 参数更改要使用的工具链。通常，除非您想调整 Java 编译器，否则不应编写此类规则。

#### 例子

一个简单的例子是：

```
java_toolchain(
    name = "toolchain",
    source_version = "7",
    target_version = "7",
    bootclasspath = ["//tools/jdk:bootclasspath"],
    xlint = [ "classfile", "divzero", "empty", "options", "path" ],
    javacopts = [ "-g" ],
    javabuilder = ":JavaBuilder_deploy.jar",
)
```

### 参数

| 属性                                  |                                                              |
| :------------------------------------ | ------------------------------------------------------------ |
| `name`                                | `Name; required`此目标的唯一名称。                           |
| `android_lint_data`                   | `List of labels; optional`android_lint_jvm_opts 中可用于标签扩展的工具标签。 |
| `android_lint_jvm_opts`               | `List of strings; optional`调用 Android Lint 时 JVM 的参数列表。 |
| `android_lint_opts`                   | `List of strings; optional`Android Lint 参数列表。           |
| `android_lint_package_configuration`  | `List of labels; optional`应应用于指定包组的 Android Lint 配置。 |
| `android_lint_runner`                 | `Label; optional`Android Lint 运行器的标签（如果有）。       |
| `bootclasspath`                       | `List of labels; optional`Java 目标引导类路径条目。对应于 javac 的 -bootclasspath 标志。 |
| `forcibly_disable_header_compilation` | `Boolean; optional; default is False`覆盖 --java_header_compilation 以在不支持它的平台上禁用头文件编译，例如 JDK 7 Bazel。 |
| `genclass`                            | `List of labels; required`GenClass 部署 jar 的标签。         |
| `header_compiler`                     | `List of labels; optional`标头编译器的标签。如果启用了 --java_header_compilation，则为必需。 |
| `header_compiler_direct`              | `List of labels; optional`头编译器的可选标签，用于不包括任何 API 生成注释处理器的直接类路径操作。此工具不支持注释处理。 |
| `ijar`                                | `List of labels; required`ijar 可执行文件的标签。            |
| `jacocorunner`                        | `Label; optional`JacocoCoverageRunner 部署 jar 的标签。      |
| `java_runtime`                        | `Label; required`与此工具链一起使用的 java_runtime。它在执行配置中默认为 java_runtime。 |
| `javabuilder`                         | `List of labels; required`JavaBuilder 部署 jar 的标签。      |
| `javabuilder_data`                    | `List of labels; optional`javabuilder_jvm_opts 中可用于标签扩展的数据标签。 |
| `javabuilder_jvm_opts`                | `List of strings; optional`调用 JavaBuilder 时 JVM 的参数列表。 |
| `javac_supports_multiplex_workers`    | `Boolean; optional; default is True`如果 JavaBuilder 支持作为 Multiplex 持久工作者运行，则为 true，否则为 false。 |
| `javac_supports_workers`              | `Boolean; optional; default is True`如果 JavaBuilder 支持作为持久工作者运行，则为 true，否则为 false。 |
| `javacopts`                           | `List of strings; optional`Java 编译器的额外参数列表。有关可能的 Java 编译器标志的详细列表，请参阅 Java 编译器文档。 |
| `jvm_opts`                            | `List of strings; optional`调用 Java 编译器时 JVM 的参数列表。请参阅 Java 虚拟机文档以获取此选项的可能标志的广泛列表。 |
| `oneversion`                          | `Label; optional`单版本强制二进制文件的标签。                |
| `oneversion_whitelist`                | `Label; optional`单版本白名单标签。                          |
| `package_configuration`               | `List of labels; optional`应应用于指定包组的配置。           |
| `proguard_allowlister`                | `Label; optional; default is @bazel_tools//tools/jdk:proguard_whitelister`Proguard 许可名单的标签。 |
| `resourcejar`                         | `List of labels; optional`资源 jar 构建器可执行文件的标签。  |
| `singlejar`                           | `List of labels; required`SingleJar 部署 jar 的标签。        |
| `source_version`                      | `String; optional`Java 源版本（例如，“6”或“7”）。它指定 Java 源代码中允许使用的代码结构集。 |
| `target_version`                      | `String; optional`Java 目标版本（例如，“6”或“7”）。它指定应该为哪个 Java 运行时构建该类。 |
| `timezone_data`                       | `Label; optional`包含时区数据的资源 jar 的标签。如果设置，则将时区数据添加为所有 java_binary 规则的隐式运行时依赖项。 |
| `tools`                               | `List of labels; optional`jvm_opts 中可用于标签扩展的工具标签。 |
| `turbine_data`                        | `List of labels; optional`Turbo_jvm_opts 中可用于标签扩展的数据标签。 |
| `turbine_jvm_opts`                    | `List of strings; optional`调用涡轮机时 JVM 的参数列表。     |
| `xlint`                               | `List of strings; optional`从默认列表中添加或删除的警告列表。在它前面加上一个破折号来删除它。有关更多信息，请参阅有关 -Xlint 选项的 Javac 文档。 |



# Python 规则

## 规则

- [py_binary](https://docs.bazel.build/versions/main/be/python.html#py_binary)
- [py_library](https://docs.bazel.build/versions/main/be/python.html#py_library)
- [py_test](https://docs.bazel.build/versions/main/be/python.html#py_test)
- [py_runtime](https://docs.bazel.build/versions/main/be/python.html#py_runtime)

## py_binary

```
py_binary(name, deps, srcs, data, args, compatible_with, deprecation, distribs, env, exec_compatible_with, exec_properties, features, imports, legacy_create_init, licenses, main, output_licenses, python_version, restricted_to, srcs_version, stamp, tags, target_compatible_with, testonly, toolchains, visibility)
```

`py_binary`是一个可执行的 Python 程序，由一组`.py`源文件（可能属于其他`py_library`规则）、一个`*.runfiles` 包含程序在运行时所需的所有代码和数据的目录树以及一个使用正确的初始环境和数据。

#### 例子

```
py_binary(
    name = "foo",
    srcs = ["foo.py"],
    data = [":transform"],  # a cc_binary which we invoke at run time
    deps = [
        ":foolib",  # a py_library
    ],
)
```

如果您想`py_binary`从另一个二进制文件或测试中运行 a（例如，运行 python 二进制文件以从 java_test 中设置一些模拟资源），那么正确的方法是使其他二进制文件或测试依赖`py_binary`于其数据部分中的. 然后另一个二进制文件可以找到`py_binary`相对于源目录的位置。

```
py_binary(
    name = "test_main",
    srcs = ["test_main.py"],
    deps = [":testlib"],
)

java_library(
    name = "testing",
    srcs = glob(["*.java"]),
    data = [":test_main"]
)
```

### 参数

| 属性                 |                                                              |
| :------------------- | ------------------------------------------------------------ |
| `name`               | `Name; required`此目标的唯一名称。 如果`main`未指定，则它应该与作为应用程序主入口点的源文件的名称相同，减去扩展名。例如，如果您的入口点被称为 `main.py`，那么您的名字应该是`main`。 |
| `deps`               | `List of labels; optional`要链接到二进制目标的其他库的列表。[ 请参阅关于所有构建规则共有](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`deps`的 属性的一般评论。这些通常是 规则。 [`py_library`](https://docs.bazel.build/versions/main/be/python.html#py_library) |
| `srcs`               | `List of labels; required`为创建目标而处理的源 ( `.py`) 文件的列表。这包括所有签入的代码和任何生成的源文件。相反，库目标属于，`deps`而运行时需要的其他二进制文件属于 `data`. |
| `imports`            | `List of strings; optional`要添加到`PYTHONPATH`.以[“使变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。这些导入目录将被添加到这个规则和依赖它的所有规则（注意：不是这个规则依赖的规则。每个目录都将被依赖于这个规则 `PYTHONPATH`的 规则添加到。[`py_binary`](https://docs.bazel.build/versions/main/be/python.html#py_binary)绝对路径（以 开头的路径`/`）和引用执行根以上路径的路径是不允许的，并且会导致错误。 |
| `legacy_create_init` | `Integer; optional; default is -1`是否在运行文件树中隐式创建空的 __init__.py 文件。这些是在包含 Python 源代码或共享库的每个目录以及这些目录的每个父目录中创建的，不包括 repo 根目录。默认值 auto 表示 true，除非 `--incompatible_default_to_explicit_init_py`使用。如果为 false，则用户负责创建（可能为空）__init__.py 文件并 `srcs`根据需要将它们添加到 Python 目标中。 |
| `main`               | `Label; optional`作为应用程序主要入口点的源文件的名称。该文件也必须列在`srcs`. 如果未指定， `name`则改为使用（见上文）。如果`name`与 中的任何文件名都不匹配`srcs`，`main`则必须指定。 |
| `python_version`     | `String; optional; nonconfigurable; default is "_INTERNAL_SENTINEL"`是否为 Python 2 或 Python 3 构建此目标（及其传递性`deps`）。有效值为`"PY2"`and `"PY3"`（默认值）。Python 版本总是被重置（可能默认情况下）为此属性指定的任何版本，而不管命令行上指定的版本或依赖此版本的其他更高目标。如果你想`select()`在当前的 Python 版本上，你可以检查`@rules_python//python:python_version`. 请参阅 [此处](https://github.com/bazelbuild/rules_python/blob/120590e2f2b66e5590bf4dc8ebef9c5338984775/python/BUILD#L43) 了解更多信息。**错误警告：**此属性设置 Bazel 构建目标的版本，但由于[#4815](https://github.com/bazelbuild/bazel/issues/4815)，生成的存根脚本可能仍会在运行时调用错误的解释器版本。请参阅 [此解决方法](https://github.com/bazelbuild/bazel/issues/4815#issuecomment-460777113)，其中包括根据需要定义一个`py_runtime`指向任一 Python 版本的目标，并`py_runtime`通过设置 `--python_top`. |
| `srcs_version`       | `String; optional; default is "PY2AND3"`此属性声明目标`srcs`与 Python 2、Python 3 或两者兼容。要实际设置 Python 运行时版本，请使用 [`python_version`](https://docs.bazel.build/versions/main/be/python.html#py_binary.python_version)可执行 Python 规则 (`py_binary`或`py_test`) 的属性。允许的值为：`"PY2AND3"`、`"PY2"`和`"PY3"`。由于历史原因，这些值`"PY2ONLY"`和`"PY3ONLY"`也是允许的，但它们本质上`"PY2"`与`"PY3"` 并且应该避免。请注意，只有可执行规则 (`py_binary`和`py_library `) 实际根据此属性的值验证当前 Python 版本。（这是一个功能；由于`py_library`不会更改当前的 Python 版本，因此如果它进行了验证，则不可能在同一调用中同时构建`PY2ONLY` 和`PY3ONLY`库。）此外，如果版本不匹配，则错误只是在执行阶段报告。特别是，错误不会出现在`bazel build --nobuild`调用中。）要获取有关哪些依赖项引入了版本要求的诊断信息，您可以`find_requirements`在目标上运行方面：`          bazel build <你的目标> \              --aspects=@rules_python//python:defs.bzl%find_requirements \              --output_groups=pyversioninfo          `这将构建一个带有后缀的文件，`-pyversioninfo.txt`提供有关为什么您的目标需要一个或另一个 Python 版本的信息。请注意，即使给定的目标由于版本冲突而无法构建，它也可以工作。 |
| `stamp`              | `Integer; optional; default is -1`是否将构建信息编码到二进制文件中。可能的值：`stamp = 1`：始终将构建信息标记到二进制文件中，即使在 [`--nostamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)构建中也是如此。**应该避免此设置**，因为它可能会杀死二进制文件的远程缓存以及依赖它的任何下游操作。`stamp = 0`：始终用常量值替换构建信息。这提供了良好的构建结果缓存。`stamp = -1`：构建信息的嵌入由 [`--[no\]stamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)标志控制。*除非它们的依赖关系发生变化，否则不会*重建标记的二进制文件。 |

## py_library

```
py_library(name, deps, srcs, data, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, features, imports, licenses, restricted_to, srcs_version, tags, target_compatible_with, testonly, visibility)
```

### 参数

| 属性           |                                                              |
| :------------- | ------------------------------------------------------------ |
| `name`         | `Name; required`此目标的唯一名称。                           |
| `deps`         | `List of labels; optional`要链接到二进制目标的其他库的列表。[ 请参阅关于所有构建规则共有](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`deps`的 属性的一般评论。这些通常是 规则。 [`py_library`](https://docs.bazel.build/versions/main/be/python.html#py_library) |
| `srcs`         | `List of labels; optional`为创建目标而处理的源 ( `.py`) 文件的列表。这包括所有签入的代码和任何生成的源文件。 |
| `imports`      | `List of strings; optional`要添加到`PYTHONPATH`.以[“使变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。这些导入目录将被添加到这个规则和依赖它的所有规则（注意：不是这个规则依赖的规则。每个目录都将被依赖于这个规则 `PYTHONPATH`的 规则添加到。[`py_binary`](https://docs.bazel.build/versions/main/be/python.html#py_binary)绝对路径（以 开头的路径`/`）和引用执行根以上路径的路径是不允许的，并且会导致错误。 |
| `srcs_version` | `String; optional; default is "PY2AND3"`此属性声明目标`srcs`与 Python 2、Python 3 或两者兼容。要实际设置 Python 运行时版本，请使用 [`python_version`](https://docs.bazel.build/versions/main/be/python.html#py_binary.python_version)可执行 Python 规则 (`py_binary`或`py_test`) 的属性。允许的值为：`"PY2AND3"`、`"PY2"`和`"PY3"`。由于历史原因，这些值`"PY2ONLY"`和`"PY3ONLY"`也是允许的，但它们本质上`"PY2"`与`"PY3"` 并且应该避免。请注意，只有可执行规则 (`py_binary`和`py_library `) 实际根据此属性的值验证当前 Python 版本。（这是一个功能；由于`py_library`不会更改当前的 Python 版本，因此如果它进行了验证，则不可能在同一调用中同时构建`PY2ONLY` 和`PY3ONLY`库。）此外，如果版本不匹配，则错误只是在执行阶段报告。特别是，错误不会出现在`bazel build --nobuild`调用中。）要获取有关哪些依赖项引入了版本要求的诊断信息，您可以`find_requirements`在目标上运行方面：`          bazel build <你的目标> \              --aspects=@rules_python//python:defs.bzl%find_requirements \              --output_groups=pyversioninfo          `这将构建一个带有后缀的文件，`-pyversioninfo.txt`提供有关为什么您的目标需要一个或另一个 Python 版本的信息。请注意，即使给定的目标由于版本冲突而无法构建，它也可以工作。 |

## py_test

```
py_test(name, deps, srcs, data, args, compatible_with, deprecation, distribs, env, env_inherit, exec_compatible_with, exec_properties, features, flaky, imports, legacy_create_init, licenses, local, main, python_version, restricted_to, shard_count, size, srcs_version, stamp, tags, target_compatible_with, testonly, timeout, toolchains, visibility)
```

`py_test()`规则编译测试 。测试是一些测试代码的二进制包装。

#### 例子

```
py_test(
    name = "runtest_test",
    srcs = ["runtest_test.py"],
    deps = [
        "//path/to/a/py/library",
    ],
)
```

也可以指定一个主模块：

```
py_test(
    name = "runtest_test",
    srcs = [
        "runtest_main.py",
        "runtest_lib.py",
    ],
    main = "runtest_main.py",
)
```

### 参数

| 属性                 |                                                              |
| :------------------- | ------------------------------------------------------------ |
| `name`               | `Name; required`此目标的唯一名称。                           |
| `deps`               | `List of labels; optional`要链接到二进制目标的其他库的列表。[ 请参阅关于所有构建规则共有](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes)`deps`的 属性的一般评论。这些通常是 规则。 [`py_library`](https://docs.bazel.build/versions/main/be/python.html#py_library) |
| `srcs`               | `List of labels; required`为创建目标而处理的源 ( `.py`) 文件的列表。这包括所有签入的代码和任何生成的源文件。相反，库目标属于，`deps`而运行时需要的其他二进制文件属于 `data`. |
| `imports`            | `List of strings; optional`要添加到`PYTHONPATH`.以[“使变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换为准。这些导入目录将被添加到这个规则和依赖它的所有规则（注意：不是这个规则依赖的规则。每个目录都将被依赖于这个规则 `PYTHONPATH`的 规则添加到。[`py_binary`](https://docs.bazel.build/versions/main/be/python.html#py_binary)绝对路径（以 开头的路径`/`）和引用执行根以上路径的路径是不允许的，并且会导致错误。 |
| `legacy_create_init` | `Integer; optional; default is -1`是否在运行文件树中隐式创建空的 __init__.py 文件。这些是在包含 Python 源代码或共享库的每个目录以及这些目录的每个父目录中创建的，不包括 repo 根目录。默认值 auto 表示 true，除非 `--incompatible_default_to_explicit_init_py`使用。如果为 false，则用户负责创建（可能为空）__init__.py 文件并 `srcs`根据需要将它们添加到 Python 目标中。 |
| `main`               | `Label; optional`作为应用程序主要入口点的源文件的名称。该文件也必须列在`srcs`. 如果未指定， `name`则改为使用（见上文）。如果`name`与 中的任何文件名都不匹配`srcs`，`main`则必须指定。 |
| `python_version`     | `String; optional; nonconfigurable; default is "_INTERNAL_SENTINEL"`是否为 Python 2 或 Python 3 构建此目标（及其传递性`deps`）。有效值为`"PY2"`and `"PY3"`（默认值）。Python 版本总是被重置（可能默认情况下）为此属性指定的任何版本，而不管命令行上指定的版本或依赖此版本的其他更高目标。如果你想`select()`在当前的 Python 版本上，你可以检查`@rules_python//python:python_version`. 请参阅 [此处](https://github.com/bazelbuild/rules_python/blob/120590e2f2b66e5590bf4dc8ebef9c5338984775/python/BUILD#L43) 了解更多信息。**错误警告：**此属性设置 Bazel 构建目标的版本，但由于[#4815](https://github.com/bazelbuild/bazel/issues/4815)，生成的存根脚本可能仍会在运行时调用错误的解释器版本。请参阅 [此解决方法](https://github.com/bazelbuild/bazel/issues/4815#issuecomment-460777113)，其中包括根据需要定义一个`py_runtime`指向任一 Python 版本的目标，并`py_runtime`通过设置 `--python_top`. |
| `srcs_version`       | `String; optional; default is "PY2AND3"`此属性声明目标`srcs`与 Python 2、Python 3 或两者兼容。要实际设置 Python 运行时版本，请使用 [`python_version`](https://docs.bazel.build/versions/main/be/python.html#py_binary.python_version)可执行 Python 规则 (`py_binary`或`py_test`) 的属性。允许的值为：`"PY2AND3"`、`"PY2"`和`"PY3"`。由于历史原因，这些值`"PY2ONLY"`和`"PY3ONLY"`也是允许的，但它们本质上`"PY2"`与`"PY3"` 并且应该避免。请注意，只有可执行规则 (`py_binary`和`py_library `) 实际根据此属性的值验证当前 Python 版本。（这是一个功能；由于`py_library`不会更改当前的 Python 版本，因此如果它进行了验证，则不可能在同一调用中同时构建`PY2ONLY` 和`PY3ONLY`库。）此外，如果版本不匹配，则错误只是在执行阶段报告。特别是，错误不会出现在`bazel build --nobuild`调用中。）要获取有关哪些依赖项引入了版本要求的诊断信息，您可以`find_requirements`在目标上运行方面：`          bazel build <你的目标> \              --aspects=@rules_python//python:defs.bzl%find_requirements \              --output_groups=pyversioninfo          `这将构建一个带有后缀的文件，`-pyversioninfo.txt`提供有关为什么您的目标需要一个或另一个 Python 版本的信息。请注意，即使给定的目标由于版本冲突而无法构建，它也可以工作。 |
| `stamp`              | `Integer; optional; default is 0`请参阅有关[py_binary()](https://docs.bazel.build/versions/main/be/python.html#py_binary_args)参数的部分，但默认情况下将 stamp 参数设置为 0 以进行测试。 |

## py_runtime

```
py_runtime(name, compatible_with, deprecation, distribs, features, files, interpreter, interpreter_path, licenses, python_version, restricted_to, stub_shebang, tags, target_compatible_with, testonly, visibility)
```

表示用于执行 Python 代码的 Python 运行时。

`py_runtime`目标可以代表平台*运行时*或 *内置运行时*。平台运行时以已知路径访问系统安装的解释器，而内置运行时指向充当解释器的可执行目标。在这两种情况下，“解释器”是指能够运行在命令行上传递的 Python 脚本的任何可执行二进制文件或包装脚本，遵循与标准 CPython 解释器相同的约定。

平台运行时本质上是非封闭的。它要求目标平台有一个位于特定路径的解释器。内置运行时可能是封闭的，也可能不是封闭的，这取决于它是指向签入的解释器还是访问系统解释器的包装脚本。

#### 例子：

```
py_runtime(
    name = "python-2.7.12",
    files = glob(["python-2.7.12/**"]),
    interpreter = "python-2.7.12/bin/python",
)

py_runtime(
    name = "python-3.6.0",
    interpreter_path = "/opt/pyenv/versions/3.6.0/bin/python",
)
```

### 参数

| 属性               |                                                              |
| :----------------- | ------------------------------------------------------------ |
| `name`             | `Name; required`此目标的唯一名称。                           |
| `files`            | `List of labels; optional`对于内置运行时，这是包含此运行时的文件集。这些文件将添加到使用此运行时的 Python 二进制文件的运行文件中。对于平台运行时，不得设置此属性。 |
| `interpreter`      | `Label; optional`对于内置运行时，这是作为解释器调用的目标。对于平台运行时，不得设置此属性。 |
| `interpreter_path` | `String; optional`对于平台运行时，这是目标平台上 Python 解释器的绝对路径。对于内置运行时，不得设置此属性。 |
| `python_version`   | `String; optional; default is "_INTERNAL_SENTINEL"`此运行时是否适用于 Python 主要版本 2 或 3。有效值为`"PY2"` 和`"PY3"`。默认值由`--incompatible_py3_is_default`标志控制。但是，将来此属性将是强制性的并且没有默认值。 |
| `stub_shebang`     | `String; optional; default is "#!/usr/bin/env python3"``py_binary`执行目标 时使用的引导 Python 存根脚本前面的“Shebang”表达式。有关动机，请参阅[问题 8685](https://github.com/bazelbuild/bazel/issues/8685)。不适用于 Windows。 |



# Android Rules

## 规则

- [android_binary](https://docs.bazel.build/versions/main/be/android.html#android_binary)
- [aar_import](https://docs.bazel.build/versions/main/be/android.html#aar_import)
- [android_library](https://docs.bazel.build/versions/main/be/android.html#android_library)
- [android_instrumentation_test](https://docs.bazel.build/versions/main/be/android.html#android_instrumentation_test)
- [android_local_test](https://docs.bazel.build/versions/main/be/android.html#android_local_test)
- [android_device](https://docs.bazel.build/versions/main/be/android.html#android_device)
- [android_ndk_repository](https://docs.bazel.build/versions/main/be/android.html#android_ndk_repository)
- [android_sdk_repository](https://docs.bazel.build/versions/main/be/android.html#android_sdk_repository)

## android_binary

```
android_binary(name, deps, srcs, assets, assets_dir, compatible_with, crunch_png, custom_package, debug_key, debug_signing_keys, debug_signing_lineage_file, densities, deprecation, dex_shards, dexopts, distribs, enable_data_binding, exec_compatible_with, exec_properties, features, incremental_dexing, instruments, javacopts, key_rotation_min_sdk, licenses, main_dex_list, main_dex_list_opts, main_dex_proguard_specs, manifest, manifest_values, multidex, nocompress_extensions, package_id, plugins, proguard_apply_dictionary, proguard_apply_mapping, proguard_generate_mapping, proguard_specs, resource_configuration_filters, resource_files, restricted_to, shrink_resources, tags, target_compatible_with, testonly, visibility)
```

生成 Android 应用程序包文件 (.apk)。

#### 隐式输出目标

- `name.apk`[ : 一个带有调试密钥和zipaligned](http://developer.android.com/guide/developing/tools/zipalign.html)签名的 Android 应用程序包文件 ，可用于开发和调试您的应用程序。使用调试密钥签名后，您无法释放您的应用程序。

- `name_unsigned.apk`：上述文件的未签名版本，可以在向公众发布之前使用发布密钥进行签名。

- ```
  name_deploy.jar
  ```

  : 包含此目标的传递闭包的 Java 存档。

  部署 jar 包含类加载器将找到的所有类，该类加载器从头到尾搜索此目标的运行时类路径。

- `name_proguard.jar`：包含在 `name_deploy.jar`. [仅当指定proguard_specs](https://docs.bazel.build/versions/main/be/android.html#android_binary.proguard_specs)属性 时才会生成此输出 。

- `name_proguard.map`：在`name_deploy.jar`. [仅当指定了proguard_specs](https://docs.bazel.build/versions/main/be/android.html#android_binary.proguard_specs)属性并 设置了[proguard_generate_mapping](https://docs.bazel.build/versions/main/be/android.html#android_binary.proguard_generate_mapping) 或[shrink_resources](https://docs.bazel.build/versions/main/be/android.html#android_binary.shrink_resources)时才会生成此输出 。

#### 例子

Android 规则的示例可以在`examples/android`Bazel 源代码树的目录中找到。

### 参数

| 属性                             |                                                              |
| :------------------------------- | ------------------------------------------------------------ |
| `name`                           | `Name; required`此目标的唯一名称。                           |
| `deps`                           | `List of labels; optional`要链接到二进制目标的其他库的列表。允许的库类型是：`android_library`， `java_library`具有`android`约束和 `cc_library`包装或`.so`为 Android 目标平台生成本机库。 |
| `srcs`                           | `List of labels; optional`为创建目标而处理的源文件列表。`srcs`类型的文件`.java`被编译。 *为了可读性*，将生成的`.java`源文件的名称放入`srcs`. 相反，将依赖的规则名称放在 中`srcs`，如下所述。`srcs`类型的文件`.srcjar`被解包和编译。（如果您需要生成一组带有 genrule 或构建扩展名的 .java 文件，这很有用。） |
| `assets`                         | `List of labels; optional`要打包的资产列表。这通常是目录`glob`下所有文件中的 一个`assets`。您还可以引用其他规则（任何生成文件的规则）或其他包中的导出文件，只要所有这些文件都在 `assets_dir`相应包中的目录下即可。 |
| `assets_dir`                     | `String; optional`给出文件路径的字符串`assets`。配对`assets`和`assets_dir`描述打包的资产，或者两个属性都应该提供，或者都不提供。 |
| `crunch_png`                     | `Boolean; optional; default is True`进行 PNG 处理（或不处理）。这独立于九个补丁处理，它总是完成的。这是已在 aapt2 中修复的 [aapt 错误](https://code.google.com/p/android/issues/detail?id=74334)的已弃用解决方法。 |
| `custom_package`                 | `String; optional`将为其生成 java 源的 Java 包。默认情况下，包是从包含规则的 BUILD 文件所在的目录推断出来的。您可以指定一个不同的包，但强烈建议不要这样做，因为它可能会引入与其他库的类路径冲突，这些冲突只会在运行时检测到。 |
| `debug_key`                      | `Label; optional; default is @bazel_tools//tools/android:debug_keystore`包含用于签署调试 apk 的调试密钥库的文件。通常你不想使用默认键以外的键，所以应该省略这个属性。*警告：不要使用您的生产密钥，它们应该受到严格保护，不要保存在您的源代码树*中。 |
| `debug_signing_keys`             | `List of labels; optional`文件列表，用于签署调试 apk 的调试密钥库。通常你不想使用默认键以外的键，所以应该省略这个属性。*警告：不要使用您的生产密钥，它们应该受到严格保护，不要保存在您的源代码树*中。 |
| `debug_signing_lineage_file`     | `Label; optional`包含 debug_signing_keys 签名沿袭的文件。通常你不想使用默认键以外的键，所以应该省略这个属性。*警告：不要使用您的生产密钥，它们应该受到严格保护，不要保存在您的源代码树*中。 |
| `densities`                      | `List of strings; optional`构建 apk 时要过滤的密度。这将去除具有指定屏幕密度的设备无法加载的光栅可绘制资源，以减小 APK 大小。如果清单中尚未包含超集列表，则相应的 compatible-screens 部分也将添加到清单中。 |
| `dex_shards`                     | `Integer; optional; default is 1`应该将 dexing 的分片数分解成。这使得 dexing 更快，但代价是应用程序安装和启动时间。二进制文件越大，应使用的分片越多。25 是一个很好的开始尝试的值。请注意，每个分片都会在最终应用中产生至少一个 dex。出于这个原因，不建议将其设置为大于 1 用于发布二进制文件。 |
| `dexopts`                        | `List of strings; optional`生成 classes.dex 时 dx 工具的附加命令行标志。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。 |
| `enable_data_binding`            | `Boolean; optional; default is False`如果为真，则此规则处理 此测试使用的启用数据绑定的依赖项中使用的[数据绑定引用。](https://developer.android.com/topic/libraries/data-binding/index.html)如果没有此设置，数据绑定依赖项将没有必要的二进制级代码生成，并且可能会产生构建失败。 |
| `incremental_dexing`             | `Integer; optional; nonconfigurable; default is -1`强制使用或不使用增量 dexing、覆盖默认值和 --incremental_dexing 标志来构建目标。 |
| `instruments`                    | `Label; optional`要检测的`android_binary`目标。如果设置了此属性，这`android_binary`将被视为仪器测试的测试应用程序。然后，`android_instrumentation_test` 目标可以在其 [test_app](https://docs.bazel.build/versions/main/be/android.html#android_instrumentation_test.test_app)属性中指定此目标。 |
| `javacopts`                      | `List of strings; optional`此目标的额外编译器选项。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。这些编译器选项在全局编译器选项之后传递给 javac。 |
| `key_rotation_min_sdk`           | `String; optional`设置应使用 APK 的旋转签名密钥生成 APK 签名的最低 Android 平台版本（API 级别）。APK 的原始签名密钥将用于所有以前的平台版本。 |
| `main_dex_list`                  | `Label; optional`一个文本文件包含一个类文件名列表。由这些类文件定义的类放在主要的 classes.dex 中。例如：`          android/support/multidex/MultiDex$V19.class          android/support/multidex/MultiDex.class          android/support/multidex/MultiDexApplication.class          com/google/common/base/Objects.class                    `必须与`multidex="manual_main_dex"`. |
| `main_dex_list_opts`             | `List of strings; optional`传递给主 dex 列表构建器的命令行选项。使用此选项可影响主 dex 列表中包含的类。 |
| `main_dex_proguard_specs`        | `List of labels; optional`用作 Proguard 规范的文件，以确定必须保留在主 dex 中的类。仅当`multidex`属性设置为时才允许`legacy`。 |
| `manifest`                       | `Label; required`Android 清单文件的名称，通常为`AndroidManifest.xml`. 如果定义了 resource_files 或 assets，则必须定义。 |
| `manifest_values`                | `Dictionary: String -> String; optional`要在清单中覆盖的值字典。清单中的任何 ${name} 实例都将替换为此字典中与 name 对应的值。applicationId、versionCode、versionName、minSdkVersion、targetSdkVersion 和 maxSdkVersion 也会覆盖 manifest 和 uses-sdk 标签的相应属性。packageName 将被忽略，并将从 applicationId （如果指定）或清单中的包进行设置。当 manifest_merger 设置为 legacy 时，只有 applicationId、versionCode 和 versionName 会起作用。 |
| `multidex`                       | `String; optional; default is "off"`是否将代码拆分为多个 dex 文件。 可能的值：`native`: 当超过 dex 64K 索引限制时，将代码拆分为多个 dex 文件。假定本机平台支持在运行时加载 multidex 类。 *这仅适用于 Android L 和更新版本*。`legacy`: 当超过 dex 64K 索引限制时，将代码拆分为多个 dex 文件。假设 multidex 类是通过应用程序代码加载的（即没有本地平台支持）。`manual_main_dex`: 当超过 dex 64K 索引限制时，将代码拆分为多个 dex 文件。[需要通过使用main_dex_list](https://docs.bazel.build/versions/main/be/android.html#android_binary.main_dex_list)属性在文本文件中提供类列表来指定主 dex 文件的内容 。`off`: 将所有代码编译成单个 dex 文件，即使它超出了索引限制。 |
| `nocompress_extensions`          | `List of strings; optional`在 apk 中未压缩的文件扩展名列表。 |
| `package_id`                     | `Integer; optional; default is 0`要分配给此二进制文件中资源的包 ID。有关更多信息，请参阅 AAPT2 的`--package-id`论点。这通常可以（并且应该）保持未设置，从而导致默认值 127 ( `0x7F`)。 |
| `plugins`                        | `List of labels; optional`在编译时运行的 Java 编译器插件。每当`java_plugin`构建此目标时，将运行 plugins 属性中指定的每个。插件生成的资源将包含在目标的结果 jar 中。 |
| `proguard_apply_dictionary`      | `Label; optional`用作 proguard 的映射的文件。在混淆期间重命名类和成员时要从中提取的“单词”的行分隔文件。 |
| `proguard_apply_mapping`         | `Label; optional`用作 proguard 的映射的文件。生成的映射文件`proguard_generate_mapping`将被重新用于将相同的映射应用于新构建。 |
| `proguard_generate_mapping`      | `Boolean; optional; nonconfigurable; default is False`是否生成 Proguard 映射文件。`proguard_specs`仅当指定时才会生成映射文件。该文件将列出原始和混淆的类、方法和字段名称之间的映射。*警告：如果使用此属性，Proguard 规范不应包含`-dontobfuscate`或 `-printmapping`。* |
| `proguard_specs`                 | `List of labels; optional`用作 Proguard 规范的文件。该文件将描述 Proguard 使用的规范集。 |
| `resource_configuration_filters` | `List of strings; optional`资源配置过滤器列表，例如“en”，它将 apk 中的资源限制为仅“en”配置中的资源。要启用伪本地化，请包含 `en_XA`和/或`ar_XB`伪语言环境。 |
| `resource_files`                 | `List of labels; optional`要打包的资源列表。这通常是目录`glob`下所有文件中的 一个`res`。 [生成的文件（来自 genrules）也可以在这里被Label](https://docs.bazel.build/versions/main/build-ref.html#labels) 引用 。唯一的限制是生成的输出必须与包含的任何其他资源文件位于相同的“”目录下。 `res` |
| `shrink_resources`               | `Integer; optional; default is -1`是否进行资源收缩。二进制文件未使用的资源将从 APK 中删除。这仅支持使用本地资源（即 `manifest`和`resource_files`属性）的规则，并且需要 ProGuard。它的运行方式与 Gradle 资源收缩器 (https://developer.android.com/studio/build/shrink-code.html#shrink-resources) 基本相同。显着差异：中的资源`values/`以及基于文件的资源将被删除`strict mode`默认使用仅 aapt2 支持删除未使用的 ID 资源如果启用了资源收缩，`name_files/resource_shrinker.log` 也会生成，详细说明执行的分析和删除。可能的值：`shrink_resources = 1`: 开启 Android 资源收缩`shrink_resources = 0`: 关闭 Android 资源收缩`shrink_resources = -1`：收缩由 [--android_resource_shrinking](https://docs.bazel.build/versions/main/user-manual.html#flag--android_resource_shrinking)标志控制。 |

## aar_import

```
aar_import(name, deps, data, aar, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, exports, features, licenses, restricted_to, srcjar, tags, target_compatible_with, testonly, visibility)
```

此规则允许将`.aar`文件用作 `android_library`和 `android_binary`规则的库。

#### 例子

```
	 aar_import(
        name = "google-vr-sdk",
        aar = "gvr-android-sdk/libraries/sdk-common-1.10.0.aar",
    )

    android_binary(
        name = "app",
        manifest = "AndroidManifest.xml",
        srcs = glob(["**.java"]),
        deps = [":google-vr-sdk"],
    )
```

### 参数

| 属性      |                                                              |
| :-------- | ------------------------------------------------------------ |
| `name`    | `Name; required`此目标的唯一名称。                           |
| `aar`     | `Label; required``.aar`提供给依赖此目标的 Android 目标 的文件。 |
| `exports` | `List of labels; optional`要导出到依赖此规则的规则的目标。请参阅[java_library.exports。](https://docs.bazel.build/versions/main/be/java.html#java_library.exports) |
| `srcjar`  | `Label; optional`一个 JAR 文件，其中包含 AAR 中已编译 JAR 文件的源代码。 |

## android_library

```
android_library(name, deps, srcs, data, assets, assets_dir, compatible_with, custom_package, deprecation, distribs, enable_data_binding, exec_compatible_with, exec_properties, exported_plugins, exports, exports_manifest, features, idl_import_root, idl_parcelables, idl_preprocessed, idl_srcs, javacopts, licenses, manifest, neverlink, plugins, proguard_specs, resource_files, restricted_to, tags, target_compatible_with, testonly, visibility)
```

该规则将其源代码编译并归档到一个`.jar`文件中。Android 运行时库`android.jar`被隐式放置在编译类路径中。

#### 隐式输出目标

- `libname.jar`: 一个 Java 档案。
- `libname-src.jar`：包含源的存档（“source jar”）。
- `name.aar`：一个包含此目标的 java 存档和资源的 android 'aar' 包。它不包含传递闭包。

#### 例子

Android 规则的示例可以在`examples/android`Bazel 源代码树的目录中找到。

以下示例显示了如何设置`idl_import_root`. 让`//java/bazel/helloandroid/BUILD`包含：

```
android_library(
    name = "parcelable",
    srcs = ["MyParcelable.java"], # bazel.helloandroid.MyParcelable

    # MyParcelable.aidl will be used as import for other .aidl
    # files that depend on it, but will not be compiled.
    idl_parcelables = ["MyParcelable.aidl"] # bazel.helloandroid.MyParcelable

    # We don't need to specify idl_import_root since the aidl file
    # which declares bazel.helloandroid.MyParcelable
    # is present at java/bazel/helloandroid/MyParcelable.aidl
    # underneath a java root (java/).
)

android_library(
    name = "foreign_parcelable",
    srcs = ["src/android/helloandroid/OtherParcelable.java"], # android.helloandroid.OtherParcelable
    idl_parcelables = [
        "src/android/helloandroid/OtherParcelable.aidl" # android.helloandroid.OtherParcelable
    ],

    # We need to specify idl_import_root because the aidl file which
    # declares android.helloandroid.OtherParcelable is not positioned
    # at android/helloandroid/OtherParcelable.aidl under a normal java root.
    # Setting idl_import_root to "src" in //java/bazel/helloandroid
    # adds java/bazel/helloandroid/src to the list of roots
    # the aidl compiler will search for imported types.
    idl_import_root = "src",
)

# Here, OtherInterface.aidl has an "import android.helloandroid.CallbackInterface;" statement.
android_library(
    name = "foreign_interface",
    idl_srcs = [
        "src/android/helloandroid/OtherInterface.aidl" # android.helloandroid.OtherInterface
        "src/android/helloandroid/CallbackInterface.aidl" # android.helloandroid.CallbackInterface
    ],

    # As above, idl_srcs which are not correctly positioned under a java root
    # must have idl_import_root set. Otherwise, OtherInterface (or any other
    # interface in a library which depends on this one) will not be able
    # to find CallbackInterface when it is imported.
    idl_import_root = "src",
)

# MyParcelable.aidl is imported by MyInterface.aidl, so the generated
# MyInterface.java requires MyParcelable.class at compile time.
# Depending on :parcelable ensures that aidl compilation of MyInterface.aidl
# specifies the correct import roots and can access MyParcelable.aidl, and
# makes MyParcelable.class available to Java compilation of MyInterface.java
# as usual.
android_library(
    name = "idl",
    idl_srcs = ["MyInterface.aidl"],
    deps = [":parcelable"],
)

# Here, ServiceParcelable uses and thus depends on ParcelableService,
# when it's compiled, but ParcelableService also uses ServiceParcelable,
# which creates a circular dependency.
# As a result, these files must be compiled together, in the same android_library.
android_library(
    name = "circular_dependencies",
    srcs = ["ServiceParcelable.java"],
    idl_srcs = ["ParcelableService.aidl"],
    idl_parcelables = ["ServiceParcelable.aidl"],
)
```

### 参数

| 属性                  |                                                              |
| :-------------------- | ------------------------------------------------------------ |
| `name`                | `Name; required`此目标的唯一名称。                           |
| `deps`                | `List of labels; optional`要链接的其他库的列表。允许的库类型是：`android_library`， `java_library`具有`android`约束和 `cc_library`包装或`.so`为 Android 目标平台生成本机库。 |
| `srcs`                | `List of labels; optional`为创建目标而处理的文件 `.java`列表 。`.srcjar``srcs`类型的文件`.java`被编译。 *为了可读性*，将生成的`.java`源文件的名称放入`srcs`. 相反，将依赖的规则名称放在 中`srcs`，如下所述。`srcs`类型的文件`.srcjar`被解包和编译。（如果您需要生成一组带有 genrule 或构建扩展名的 .java 文件，这很有用。）如果`srcs`省略， `deps`则从该规则中导出任何指定的依赖项（有关导出依赖项的更多信息，请参阅 [java_library 的](https://docs.bazel.build/versions/main/be/java.html#java_library.exports)导出）。但是，这种行为很快就会被弃用；尽量不要依赖它。 |
| `assets`              | `List of labels; optional`要打包的资产列表。这通常是目录`glob`下所有文件中的 一个`assets`。您还可以引用其他规则（任何生成文件的规则）或其他包中的导出文件，只要所有这些文件都在 `assets_dir`相应包中的目录下即可。 |
| `assets_dir`          | `String; optional`给出文件路径的字符串`assets`。配对`assets`和`assets_dir`描述打包的资产，或者两个属性都应该提供，或者都不提供。 |
| `custom_package`      | `String; optional`将为其生成 java 源的 Java 包。默认情况下，包是从包含规则的 BUILD 文件所在的目录推断出来的。您可以指定一个不同的包，但强烈建议不要这样做，因为它可能会引入与其他库的类路径冲突，这些冲突只会在运行时检测到。 |
| `enable_data_binding` | `Boolean; optional; default is False`如果为真，则此规则处理 此测试使用的启用数据绑定的依赖项中使用的[数据绑定引用。](https://developer.android.com/topic/libraries/data-binding/index.html)如果没有此设置，数据绑定依赖项将没有必要的二进制级代码生成，并且可能会产生构建失败。 |
| `exported_plugins`    | `List of labels; optional``java_plugin`要导出到直接依赖于该库的库 的 s 列表（例如注释处理器）。指定的`java_plugin`s 列表将应用于直接依赖于该库的任何库，就好像该库已在`plugins`. |
| `exports`             | `List of labels; optional`通过`exports`属性达到的所有规则的闭包被认为是直接依赖于目标的任何规则的直接依赖项`exports`。他们`exports`不是他们所属规则的直接部门。 |
| `exports_manifest`    | `Integer; optional; default is 1`是否将清单条目导出到`android_binary`依赖于此目标的目标。`uses-permissions`永远不会导出属性。 |
| `idl_import_root`     | `String; optional`包含此库中包含的 idl 源的 java 包树根的包相对路径。在处理依赖此库的 idl 源时，此路径将用作导入根。指定时`idl_import_root`，两者`idl_parcelables` 和都`idl_srcs`必须位于它们所代表的对象的 java 包指定的路径`idl_import_root`。`idl_import_root`未指定时，两者和`idl_parcelables`都`idl_srcs`必须位于其包指定的 Java 根目录下的路径中。请参阅[ 示例](https://docs.bazel.build/versions/main/be/android.html#android_library_examples.idl_import_root)。 |
| `idl_parcelables`     | `List of labels; optional`作为导入提供的 Android IDL 定义列表。这些文件将 `android_library`直接或通过其传递闭包作为依赖于该库的任何目标的导入提供，但不会被转换为 Java 或编译。仅应包含与此库中的源`.aidl`直接对应的文件 `.java`（例如，Parcelable 的自定义实现），否则`idl_srcs`应使用。这些文件必须适当放置，以便aidl 编译器找到它们。 有关这意味着什么的信息，请参阅[idl_import_root 的描述。](https://docs.bazel.build/versions/main/be/android.html#android_library.idl_import_root) |
| `idl_preprocessed`    | `List of labels; optional`作为导入提供的预处理 Android IDL 定义列表。这些文件将 `android_library`直接或通过其传递闭包作为依赖于该库的任何目标的导入提供，但不会被转换为 Java 或编译。`.aidl`仅应包含与此库中的源直接对应的 预处理文件`.java`（例如，Parcelable 的自定义实现），否则`idl_srcs`用于需要转换为 Java 接口的 Android IDL 定义和`idl_parcelable` 用于未预处理的 AIDL 文件。 |
| `idl_srcs`            | `List of labels; optional`要转换为 Java 接口的 Android IDL 定义列表。Java 接口生成后，会与`srcs`.这些文件将 `android_library`直接或通过其传递闭包作为依赖于该库的任何目标的导入提供。这些文件必须适当放置，以便aidl 编译器找到它们。 有关这意味着什么的信息，请参阅[idl_import_root 的描述。](https://docs.bazel.build/versions/main/be/android.html#android_library.idl_import_root) |
| `javacopts`           | `List of strings; optional`此目标的额外编译器选项。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。这些编译器选项在全局编译器选项之后传递给 javac。 |
| `manifest`            | `Label; optional`Android 清单文件的名称，通常为`AndroidManifest.xml`. 如果定义了 resource_files 或 assets，则必须定义。 |
| `neverlink`           | `Boolean; optional; default is False`仅将此库用于编译而不是在运行时。标记为的规则的输出`neverlink`不会用于 `.apk`创建。如果库将在执行期间由运行时环境提供，则很有用。 |
| `plugins`             | `List of labels; optional`在编译时运行的 Java 编译器插件。每当`java_plugin`构建此目标时，将运行 plugins 属性中指定的每个。插件生成的资源将包含在目标的结果 jar 中。 |
| `proguard_specs`      | `List of labels; optional`用作 Proguard 规范的文件。这些将描述 Proguard 使用的规范集。如果指定，它们将`android_binary`根据此库添加到任何目标。这里包含的文件必须只有幂等规则，即-dontnote、-dontwarn、assumenosideeffects，以及以-keep开头的规则。其他选项只能出现在 `android_binary`的 proguard_specs 中，以确保非重言式合并。 |
| `resource_files`      | `List of labels; optional`要打包的资源列表。这通常是目录`glob`下所有文件中的 一个`res`。 [生成的文件（来自 genrules）也可以在这里被Label](https://docs.bazel.build/versions/main/build-ref.html#labels) 引用 。唯一的限制是生成的输出必须与包含的任何其他资源文件位于相同的“”目录下。 `res` |

## android_instrumentation_test

```
android_instrumentation_test(name, data, args, compatible_with, deprecation, distribs, env, env_inherit, exec_compatible_with, exec_properties, features, flaky, licenses, local, restricted_to, shard_count, size, support_apks, tags, target_compatible_with, target_device, test_app, testonly, timeout, toolchains, visibility)
```

一条`android_instrumentation_test`规则运行 Android 检测测试。它将启动一个模拟器，安装正在测试的应用程序、测试应用程序和任何其他需要的应用程序，并运行测试包中定义的测试。

test_app属性指定 [哪个](https://docs.bazel.build/versions/main/be/android.html#android_instrumentation_test.test_app)`android_binary`包含测试。这`android_binary`反过来又通过它的[instruments](https://docs.bazel.build/versions/main/be/android.html#android_binary.instruments)属性 指定`android_binary`被测应用程序 。

#### 例子

```
# java/com/samples/hello_world/BUILD

android_library(
    name = "hello_world_lib",
    srcs = ["Lib.java"],
    manifest = "LibraryManifest.xml",
    resource_files = glob(["res/**"]),
)

# The app under test
android_binary(
    name = "hello_world_app",
    manifest = "AndroidManifest.xml",
    deps = [":hello_world_lib"],
)
# javatests/com/samples/hello_world/BUILD

android_library(
    name = "hello_world_test_lib",
    srcs = ["Tests.java"],
    deps = [
      "//java/com/samples/hello_world:hello_world_lib",
      ...  # test dependencies such as Espresso and Mockito
    ],
)

# The test app
android_binary(
    name = "hello_world_test_app",
    instruments = "//java/com/samples/hello_world:hello_world_app",
    manifest = "AndroidManifest.xml",
    deps = [":hello_world_test_lib"],
)

android_instrumentation_test(
    name = "hello_world_uiinstrumentation_tests",
    target_device = ":some_target_device",
    test_app = ":hello_world_test_app",
)
```

### 参数

| 属性            |                                                              |
| :-------------- | ------------------------------------------------------------ |
| `name`          | `Name; required`此目标的唯一名称。                           |
| `support_apks`  | `List of labels; optional`在仪器测试开始之前要在设备上安装的其他 APK。 |
| `target_device` | `Label; required`测试应该运行的[android_device 。](https://docs.bazel.build/versions/main/be/android.html#android_device)要在已经运行的模拟器或物理设备上运行测试，请使用以下参数： `--test_output=streamed --test_arg=--device_broker_type=LOCAL_ADB_SERVER --test_arg=--device_serial_number=$device_identifier` |
| `test_app`      | `Label; required`包含测试类 的[android_binary目标。](https://docs.bazel.build/versions/main/be/android.html#android_binary)目标必须通过其属性 `android_binary`指定它正在测试的目标。[`instruments`](https://docs.bazel.build/versions/main/be/android.html#android_binary.instruments) |

## android_local_test

```
android_local_test(name, deps, srcs, data, args, compatible_with, custom_package, densities, deprecation, env, env_inherit, exec_compatible_with, exec_properties, features, flaky, javacopts, jvm_flags, licenses, local, manifest, manifest_values, nocompress_extensions, plugins, resource_configuration_filters, resource_jars, resource_strip_prefix, restricted_to, runtime_deps, shard_count, size, stamp, tags, target_compatible_with, test_class, testonly, timeout, toolchains, use_launcher, visibility)
```

`android_library`此规则适用于本地（而不是在设备上） 的单元测试规则。它适用于 Android Robolectric 测试框架。有关编写 Robolectric 测试的详细信息，请参阅[Android Robolectric](http://robolectric.org/)网站。

#### 隐式输出目标

- `name.jar`: 测试的 Java 存档。
- `name-src.jar`：包含源的存档（“source jar”）。
- `name_deploy.jar`：适合部署的 Java 部署存档（仅在明确要求时构建）。

#### 例子

要将 Robolectric 与 一起使用`android_local_test`，请将 [Robolectric 的存储库](https://github.com/robolectric/robolectric-bazel/tree/master/bazel)添加到您的`WORKSPACE`文件中：

```
http_archive(
    name = "robolectric",
    urls = ["https://github.com/robolectric/robolectric/archive/<COMMIT>.tar.gz"],
    strip_prefix = "robolectric-<COMMIT>",
    sha256 = "<HASH>",
)
load("@robolectric//bazel:robolectric.bzl", "robolectric_repositories")
robolectric_repositories()
```

这`maven_jar`引入了 Robolectric 所需的规则。那么每个`android_local_test`规则都应该依赖于 `@robolectric//bazel:robolectric`. 请参见下面的示例。



```
android_local_test(
    name = "SampleTest",
    srcs = [
        "SampleTest.java",
    ],
    manifest = "LibManifest.xml",
    deps = [
        ":sample_test_lib",
        "@robolectric//bazel:robolectric",
    ],
)

android_library(
    name = "sample_test_lib",
    srcs = [
         "Lib.java",
    ],
    resource_files = glob(["res/**"]),
    manifest = "AndroidManifest.xml",
)
```

### 参数

| 属性                             |                                                              |
| :------------------------------- | ------------------------------------------------------------ |
| `name`                           | `Name; required`此目标的唯一名称。                           |
| `deps`                           | `List of labels; optional`要测试的库列表以及要链接到目标的其他库。在此属性的传递闭包中，在 Android 规则中声明的所有资源、资产和清单文件都在测试中可用。中的允许规则列表`deps`是`android_library`、 `aar_import`、`java_import`、`java_library`和`java_lite_proto_library`。 |
| `srcs`                           | `List of labels; optional`为创建目标而处理的源文件列表。除非在下面描述的特殊情况下，否则是必需的。`srcs`类型的文件`.java`被编译。 *为了可读性*，将生成的`.java`源文件的名称放入`srcs`. 相反，将依赖的规则名称放在 中`srcs`，如下所述。`srcs`类型的文件`.srcjar`被解包和编译。（如果您需要生成一组带有 genrule 或构建扩展名的 .java 文件，这很有用。）只要存在至少一个上述文件类型的文件，所有其他文件都将被忽略。否则会引发错误。该`srcs`属性是必需的，不能为空，除非 `runtime_deps`指定。 |
| `custom_package`                 | `String; optional`将在其中生成 R 类的 Java 包。默认情况下，包是从包含规则的 BUILD 文件所在的目录推断出来的。如果您使用此属性，您可能也需要使用`test_class`。 |
| `densities`                      | `List of strings; optional`构建 apk 时要过滤的密度。如果清单中尚未包含超集 StarlarkListing，则相应的 compatible-screens 部分也将添加到清单中。 |
| `javacopts`                      | `List of strings; optional`此库的额外编译器选项。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。这些编译器选项在全局编译器选项之后传递给 javac。 |
| `jvm_flags`                      | `List of strings; optional`要嵌入到为运行此二进制文件而生成的包装脚本中的标志列表。受限于[$(location)](https://docs.bazel.build/versions/main/be/make-variables.html#location)和 [“Make variable”](https://docs.bazel.build/versions/main/be/make-variables.html)替换，以及 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。Java 二进制文件的包装脚本包含一个 CLASSPATH 定义（用于查找所有相关的 jar）并调用正确的 Java 解释器。包装脚本生成的命令行包括主类的名称，后跟a `"$@"`，因此您可以在类名之后传递其他参数。但是，用于 JVM 解析的参数必须在命令行上的类名*之前指定。*的内容`jvm_flags`在列出类名之前添加到包装脚本中。请注意，此属性对 输出*没有影响。*`*_deploy.jar` |
| `manifest`                       | `Label; optional`Android 清单文件的名称，通常为`AndroidManifest.xml`. 如果定义了 resource_files 或 assets，或者来自被测库的任何清单中包含`minSdkVersion`标签，则必须定义。 |
| `manifest_values`                | `Dictionary: String -> String; optional`要在清单中覆盖的值字典。清单中的任何 ${name} 实例都将替换为此字典中与 name 对应的值。 `applicationId`, `versionCode`, `versionName`, `minSdkVersion`,`targetSdkVersion`和 `maxSdkVersion`也会覆盖 manifest 和 uses-sdk 标签的相应属性。`packageName`将被忽略，并且将从 `applicationId`清单中的包（如果指定）或包中设置。为了使用 manifest_values，不需要在规则上有一个清单。 |
| `nocompress_extensions`          | `List of strings; optional`在资源 apk 中保留未压缩的文件扩展名列表。 |
| `plugins`                        | `List of labels; optional`在编译时运行的 Java 编译器插件。每当`java_plugin`构建此规则时，此属性中指定的每个都将运行。库也可以从使用 `exported_plugins`. 插件生成的资源将包含在此规则的生成 jar 中。 |
| `resource_configuration_filters` | `List of strings; optional`资源配置过滤器列表，例如“en”，它将 apk 中的资源限制为仅“en”配置中的资源。 |
| `resource_jars`                  | `List of labels; optional`一组包含 Java 资源的档案。如果指定，这些 jar 的内容将合并到输出 jar 中。 |
| `resource_strip_prefix`          | `String; optional`从 Java 资源中剥离的路径前缀。如果指定，则从`resources` 属性中的每个文件中删除此路径前缀。资源文件不在此目录下是错误的。如果不指定（默认），则资源文件的路径根据与源文件的Java包相同的逻辑来确定。例如，源文件 `stuff/java/foo/bar/a.txt`位于`foo/bar/a.txt`. |
| `runtime_deps`                   | `List of labels; optional`仅在运行时可用于最终二进制文件或测试的库。像普通`deps`的，这些将出现在运行时类路径中，但与它们不同的是，它们不会出现在编译时类路径中。此处应列出仅在运行时需要的依赖项。依赖分析工具应该忽略同时出现在 `runtime_deps`和中的目标`deps`。 |
| `stamp`                          | `Integer; optional; default is 0`是否将构建信息编码到二进制文件中。可能的值：`stamp = 1`：始终将构建信息标记到二进制文件中，即使在 [`--nostamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)构建中也是如此。**应该避免此设置**，因为它可能会杀死二进制文件的远程缓存以及依赖它的任何下游操作。`stamp = 0`：始终用常量值替换构建信息。这提供了良好的构建结果缓存。`stamp = -1`：构建信息的嵌入由 [`--[no\]stamp`](https://docs.bazel.build/versions/main/user-manual.html#flag--stamp)标志控制。*除非它们的依赖关系发生变化，否则不会*重建标记的二进制文件。 |
| `test_class`                     | `String; optional`要由测试运行程序加载的 Java 类。 此属性指定此测试要运行的 Java 类的名称。很少需要设置它。如果省略此参数，将使用名称对应于`name`该 `android_local_test`规则的 Java 类。测试类需要用`org.junit.runner.RunWith`. |
| `use_launcher`                   | `Boolean; optional; default is True`二进制文件是否应该使用自定义启动器。如果此属性设置为 false，则此目标的 [启动器](https://docs.bazel.build/versions/main/be/java.html#java_binary.launcher)属性和相关 [`--java_launcher`](https://docs.bazel.build/versions/main/user-manual.html#flag--java_launcher)标志将被忽略。 |

## android_device

```
android_device(name, cache, compatible_with, default_properties, deprecation, distribs, exec_compatible_with, exec_properties, features, horizontal_resolution, licenses, platform_apks, ram, restricted_to, screen_density, system_image, tags, target_compatible_with, testonly, vertical_resolution, visibility, vm_heap)
```

此规则创建一个使用给定规范配置的 android 模拟器。这个模拟器可以通过 bazel run 命令或直接执行生成的脚本来启动。鼓励依赖现有的 android_device 规则而不是定义自己的规则。

该规则是 bazel test 和 bazel run 的 --run_under 标志的合适目标。它启动一个模拟器，将正在测试/运行的目标复制到模拟器，并根据需要对其进行测试或运行。

`android_device`如果底层 [system_image](https://docs.bazel.build/versions/main/be/android.html#android_device.system_image)是基于 X86 并且最多针对 I686 CPU 架构进行了优化，则支持创建 KVM 映像。要使用 KVM，请添加 `tags = ['requires-kvm'] `到`android_device`规则中。

#### 隐式输出目标

- `name_images/userdata.dat`：包含启动模拟器的图像文件和快照
- `name_images/emulator-meta-data.pb`：包含传递给模拟器以重新启动它所必需的序列化信息。

#### 例子

以下示例展示了如何使用 android_device。 `//java/android/helloandroid/BUILD`包含

```
android_device(
    name = "nexus_s",
    cache = 32,
    default_properties = "nexus_s.properties",
    horizontal_resolution = 480,
    ram = 512,
    screen_density = 233,
    system_image = ":emulator_images_android_16_x86",
    vertical_resolution = 800,
    vm_heap = 32,
)

filegroup(
    name = "emulator_images_android_16_x86",
    srcs = glob(["androidsdk/system-images/android-16/**"]),
)
```

`//java/android/helloandroid/nexus_s.properties`包含：

```
ro.product.brand=google
ro.product.device=crespo
ro.product.manufacturer=samsung
ro.product.model=Nexus S
ro.product.name=soju
```

此规则将生成图像和启动脚本。您可以通过执行 bazel run :nexus_s -- --action=start 在本地启动模拟器。该脚本公开了以下标志：

- --adb_port：公开 adb 的端口。如果您希望向模拟器发出 adb 命令，这是您将发出 adb connect 的端口。
- --emulator_port：用于公开模拟器的 telnet 管理控制台的端口。
- --enable_display：如果为 true（默认为 false），则以显示启动模拟器。
- --action：开始或终止。
- --apks_to_install：要在模拟器上安装的 apk 列表。

### 参数

| 属性                    |                                                              |
| :---------------------- | ------------------------------------------------------------ |
| `name`                  | `Name; required`此目标的唯一名称。                           |
| `cache`                 | `Integer; required`模拟器缓存分区的大小（以 MB 为单位）。最小值为 16 兆字节。 |
| `default_properties`    | `Label; optional`要放置在模拟器上的 /default.prop 中的单个属性文件。这允许规则作者进一步配置模拟器，使其看起来更像一个真实的设备（特别是控制它的 UserAgent 字符串和其他可能导致应用程序或服务器与特定设备不同的行为）。此文件中的属性将覆盖通常由模拟器设置的只读属性，例如 ro.product.model。 |
| `horizontal_resolution` | `Integer; required`要模拟的水平屏幕分辨率（以像素为单位）。最小值为 240。 |
| `platform_apks`         | `List of labels; optional`启动时要在设备上安装的 apk 列表。  |
| `ram`                   | `Integer; required`为设备模拟的 RAM 量（以 MB 为单位）。这适用于整个设备，而不仅仅是安装在设备上的特定应用程序。最小值为 64 兆字节。 |
| `screen_density`        | `Integer; required`模拟屏幕的密度，以每英寸像素为单位。最小值为 30 ppi。 |
| `system_image`          | `Label; required`包含以下文件的文件组：system.img：系统分区kernel-qemu：模拟器将加载的 Linux 内核ramdisk.img：启动时使用的 initrd 映像userdata.img：初始用户数据分区source.properties：包含图像信息的属性文件这些文件是 android sdk 的一部分或由第三方提供（例如 Intel 提供 x86 图像）。 |
| `vertical_resolution`   | `Integer; required`要模拟的垂直屏幕分辨率（以像素为单位）。最小值为 240。 |
| `vm_heap`               | `Integer; required`Android 将用于每个进程的虚拟机堆的大小（以 MB 为单位）。最小值为 16 兆字节。 |

## android_ndk_repository

```
android_ndk_repository(name, api_level, path, repo_mapping)
```

将 Bazel 配置为使用 Android NDK 以支持使用本机代码构建 Android 目标。

请注意，为 Android 构建还需要文件`android_sdk_repository`中的规则 `WORKSPACE`。

有关更多信息，请阅读[ 有关将 Android NDK 与 Bazel 结合使用的完整文档](https://docs.bazel.build/versions/main/android-ndk.html)。

#### 例子

```
android_ndk_repository(
    name = "androidndk",
)
```

上面的示例将从中找到您的 Android NDK`$ANDROID_NDK_HOME`并检测它支持的最高 API 级别。

```
android_ndk_repository(
    name = "androidndk",
    path = "./android-ndk-r20",
    api_level = 24,
)
```

上面的示例将使用位于工作区中的 Android NDK `./android-ndk-r20`。编译 JNI 代码时，它将使用 API 级别 24 库。

#### 处理器功能

Android NDK 包含 [cpufeatures 库](https://developer.android.com/ndk/guides/cpu-features.html) ，可用于在运行时检测设备的 CPU。以下示例演示了如何将 cpufeatures 与 Bazel 一起使用。

```
# jni.cc
#include "ndk/sources/android/cpufeatures/cpu-features.h"
...
# BUILD
cc_library(
    name = "jni",
    srcs = ["jni.cc"],
    deps = ["@androidndk//:cpufeatures"],
)
```

### 参数

| 属性           |                                                              |
| :------------- | ------------------------------------------------------------ |
| `name`         | `Name; required`此目标的唯一名称。                           |
| `api_level`    | `Integer; optional; nonconfigurable; default is 0`要构建的 Android API 级别。如果未指定，将使用已安装的最高 API 级别。 |
| `path`         | `String; optional; nonconfigurable`Android NDK 的绝对或相对路径。`$ANDROID_NDK_HOME`必须设置 此属性或 环境变量。Android NDK 可以从 [Android 开发者网站 ](https://developer.android.com/ndk/downloads/index.html)下载。 |
| `repo_mapping` | `Dictionary: String -> String; optional`从本地存储库名称到全局存储库名称的字典。这允许控制此存储库的依赖项的工作区依赖项解析。例如，一个条目`"@foo": "@bar"`声明，对于此存储库依赖的任何时间`"@foo"`（例如对 的依赖 `"@foo//some:target"`），它实际上应该在全局声明的`"@bar"`( `"@bar//some:target"`) 中解决该依赖关系。 |

## android_sdk_repository

```
android_sdk_repository(name, api_level, build_tools_version, path, repo_mapping)
```

将 Bazel 配置为使用本地 Android SDK 来支持构建 Android 目标。

#### 例子

为 Bazel 设置 Android SDK 的最低要求是将`android_sdk_repository`名为“androidsdk”的规则放入您的`WORKSPACE`文件中，并将`$ANDROID_HOME` 环境变量设置为您的 Android SDK 的路径。Bazel 将默认使用 Android SDK 中安装的最高 Android API 级别和构建工具版本。

```
android_sdk_repository(
    name = "androidsdk",
)
```

为了确保可重现的构建，`path`可以将`api_level`和 `build_tools_version`属性设置为特定值。如果 Android SDK 没有安装指定的 API 级别或构建工具版本，构建将失败。

```
android_sdk_repository(
    name = "androidsdk",
    path = "./sdk",
    api_level = 19,
    build_tools_version = "25.0.0",
)
```

上面的示例还演示了使用 Android SDK 的工作空间相对路径。如果 Android SDK 是您的 Bazel 工作区的一部分（例如，如果它被检查到版本控制中），这将非常有用。

#### 支持库

支持库在 Android SDK 管理器中作为“Android 支持存储库”提供。这是一组版本化的通用 Android 库，例如 Support 和 AppCompat 库，它们被打包为本地 Maven 存储库。`android_sdk_repository`为这些库中的每一个生成 Bazel 目标，这些库可以在依赖项 `android_binary`和`android_library`目标中使用。

生成的目标的名称源自 Android 支持存储库中库的 Maven 坐标，格式为`@androidsdk//${group}:${artifact}-${version}`. 以下示例显示了如何`android_library`依赖 v7 appcompat 库的版本 25.0.0。

```
android_library(
    name = "lib",
    srcs = glob(["*.java"]),
    manifest = "AndroidManifest.xml",
    resource_files = glob(["res/**"]),
    deps = ["@androidsdk//com.android.support:appcompat-v7-25.0.0"],
)
```

### 参数

| 属性                  |                                                              |
| :-------------------- | ------------------------------------------------------------ |
| `name`                | `Name; required`此目标的唯一名称。                           |
| `api_level`           | `Integer; optional; nonconfigurable; default is 0`默认情况下构建的 Android API 级别。如果未指定，将使用已安装的最高 API 级别。用于给定构建的 API 级别可以被`android_sdk` 标志覆盖。使用 name 为 SDK 中安装的每个 API 级别`android_sdk_repository`创建一个目标，无论是否指定了此属性。例如，要针对非默认 API 级别进行构建：. `android_sdk``@androidsdk//:sdk-${level}``bazel build --android_sdk=@androidsdk//:sdk-19 //java/com/example:app`要查看`android_sdk`由 生成的所有目标`android_sdk_repository `，您可以运行`bazel query "kind(android_sdk, @androidsdk//...)"`. |
| `build_tools_version` | `String; optional; nonconfigurable`在 Android SDK 中使用的 Android 构建工具的版本。如果未指定，将使用最新安装的构建工具版本。Bazel 需要构建工具版本 30.0.0 或更高版本。 |
| `path`                | `String; optional; nonconfigurable`Android SDK 的绝对或相对路径。`$ANDROID_HOME`必须设置 此属性或 环境变量。Android SDK 可以从 [Android 开发者网站](https://developer.android.com/)下载。 |
| `repo_mapping`        | `Dictionary: String -> String; optional`从本地存储库名称到全局存储库名称的字典。这允许控制此存储库的依赖项的工作区依赖项解析。例如，一个条目`"@foo": "@bar"`声明，对于此存储库依赖的任何时间`"@foo"`（例如对 的依赖 `"@foo//some:target"`），它实际上应该在全局声明的`"@bar"`( `"@bar//some:target"`) 中解决该依赖关系。 |



# Objective-C 规则

## 规则

- [apple_static_library](https://docs.bazel.build/versions/main/be/objective-c.html#apple_static_library)
- [j2objc_library](https://docs.bazel.build/versions/main/be/objective-c.html#j2objc_library)
- [objc_import](https://docs.bazel.build/versions/main/be/objective-c.html#objc_import)
- [objc_library](https://docs.bazel.build/versions/main/be/objective-c.html#objc_library)
- [available_xcodes](https://docs.bazel.build/versions/main/be/objective-c.html#available_xcodes)
- [xcode_config](https://docs.bazel.build/versions/main/be/objective-c.html#xcode_config)
- [xcode_version](https://docs.bazel.build/versions/main/be/objective-c.html#xcode_version)

## apple_static_library

```
apple_static_library(name, deps, data, additional_linker_inputs, avoid_deps, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, features, licenses, linkopts, minimum_os_version, platform_type, restricted_to, sdk_dylibs, sdk_frameworks, tags, target_compatible_with, testonly, visibility, weak_sdk_frameworks)
```

此规则生成单架构或多架构（“fat”）Objective-C 静态链接库，通常用于创建静态 Apple 框架，以便在多个扩展或应用程序中分发和重用。

该`lipo`工具用于组合多种架构的文件；构建标志控制目标架构。检查的构建标志取决于 `platform_type`此规则的属性（并在其文档中进行了描述）。

#### 隐式输出目标

- `name_lipo.a`: 一个 'lipo'ed 存档文件。所有传递依赖项 和`srcs`都是链接的，减去在 中指定的所有传递依赖项`avoid_deps`。

### 参数

| 属性                       |                                                              |
| :------------------------- | ------------------------------------------------------------ |
| `name`                     | `Name; required`此目标的唯一名称。                           |
| `deps`                     | `List of labels; optional`链接在一起形成最终二进制文件的目标列表。 |
| `additional_linker_inputs` | `List of labels; optional`要传递给链接器的额外文件。         |
| `avoid_deps`               | `List of labels; optional`不应包含在此规则的输出中（也不包含其传递依赖项）的目标列表——即使它们通过`deps`属性传递依赖。此属性有效地用于从静态库中删除部分依赖关系树，并且在静态库相互依赖的场景中最常用。也就是说，假设静态库 X 和 C 通常分别分发给消费者。C 是一个非常常见的基础库，而 X 包含不太常见的功能；X 依赖于 C，因此寻求导入库 X 的应用程序也必须导入库 C。描述 X 的目标会将 C 的目标设置为`avoid_deps`. 这样，X 可以在不包含 C 的情况下依赖于 C。如果没有这种`avoid_deps`用法，同时导入 X 和 C 的应用程序将有 C 的重复符号。 |
| `linkopts`                 | `List of strings; optional`传递给链接器的额外标志。          |
| `minimum_os_version`       | `String; optional`应构建此目标及其依赖项的最低操作系统版本。这应该是一个带点的版本字符串，例如“7.3”。 |
| `platform_type`            | `String; required`在此规则中为其创建工件的平台类型。这决定了使用哪个 Apple 平台 SDK 进行编译/链接，以及使用哪个标志来确定要构建的架构。例如，如果`ios` 选择 ，则将创建输出二进制文件/库，并结合`--ios_multi_cpus`. 选项是：`ios`: 架构收集自`--ios_multi_cpus`.`macos`: 架构收集自`--macos_cpus`.`tvos`: 架构收集自`--tvos_cpus`.`watchos`: 架构收集自`--watchos_cpus`. |
| `sdk_dylibs`               | `List of strings; optional`要链接的 SDK .dylib 库的名称。例如，“libz”或“libarchive”。如果二进制文件在其依赖关系树中包含任何 C++ 或 Objective-C++ 源代码，则会自动包含“libc++”。链接二进制文件时，将使用在该二进制文件的传递依赖图中命名的所有库。 |
| `sdk_frameworks`           | `List of strings; optional`要链接的 SDK 框架的名称（例如“AddressBook”、“QuartzCore”）。在为 iOS、tvOS 和 watchOS 平台构建时，总是包含“UIKit”和“Foundation”。对于 macOS，始终只包含“Foundation”。链接顶级二进制文件（例如 apple_binary）时，该二进制文件的传递依赖图中列出的所有 SDK 框架都会被链接。 |
| `weak_sdk_frameworks`      | `List of strings; optional`要弱链接的 SDK 框架的名称。例如，“媒体可访问性”。与定期链接的 SDK 框架不同，如果来自弱链接框架的符号在运行时不存在，则它们不会导致错误。 |

## j2objc_library

```
j2objc_library(name, deps, compatible_with, deprecation, distribs, entry_classes, features, jre_deps, licenses, restricted_to, tags, target_compatible_with, testonly, visibility)
```

此规则使用[J2ObjC](https://github.com/google/j2objc)将 Java 源文件转换为 Objective-C，然后可以将其用作 objc_library 和 objc_binary 规则的依赖项。关于 J2ObjC 本身的详细信息可以在 [J2ObjC 站点上找到](http://j2objc.org/)

`--j2objc_translation_flags`可以使用命令行中 的构建标志指定自定义 J2ObjC 转换标志 。

请注意，j2objc_library 目标中包含的已翻译文件将使用默认编译配置进行编译，该配置与 objc_library 规则的源配置相同，但在属性中未指定编译选项。

此外，生成的代码在目标级别而不是源级别进行重复数据删除。如果您有两个包含相同 Java 源文件的不同 Java 目标，您可能会在链接时看到重复符号错误。解决此问题的正确方法是将共享的 Java 源文件移动到可以依赖的单独的公共目标中。

### 参数

| 属性            |                                                              |
| :-------------- | ------------------------------------------------------------ |
| `name`          | `Name; required`此目标的唯一名称。                           |
| `deps`          | `List of labels; optional`包含要转换为 Objective-C 的 Java 文件 的 、 和`j2objc_library`目标`java_library`的 列表。`java_import``java_proto_library`通过,可以传递到达的所有`java_library`和目标， 将被翻译和编译。目前不支持 Java 注解处理生成的文件或未指定的目标 。 `java_import``exports``deps``runtime_deps``java_import``srcjar`J2ObjC 转换的工作方式因传递闭包中包含的源 Java 源文件的类型而异。对于 of 中包含的每个 .java 源文件 `srcs`，`java_library`都会生成一个对应的 .h 和 .m 源文件。对于`srcs`of `java_library`或`srcjar`of 中包含的每个源 jar `java_import`，将生成一个对应的 .h 和 .m 源文件，其中包含该 jar 的所有代码。用户可以在他们的代码中导入 J2ObjC 生成的头文件。这些文件的导入路径是原始 Java 工件的根相对路径。例如， `//some/package/foo.java`有一个导入路径，`some/package/foo.h` 并且`//some/package/bar.srcjar`有`some/package/bar.h`如果 proto_library 规则在此规则的传递闭包中，则 J2ObjC protos 也将在二进制级别生成、编译和链接。对于 proto `//some/proto/foo.proto`，用户可以使用 import path 引用生成的代码`some/proto/foo.j2objc.pb.h`。 |
| `entry_classes` | `List of strings; optional`用户 ObjC 代码将直接引用其翻译的 ObjC 对应项的 Java 类列表。如果标志`--j2objc_dead_code_removal `打开，则需要此属性。Java 类的规范名称应由 [Java 语言规范定义。](http://docs.oracle.com/javase/specs/jls/se8/html/jls-6.html#jls-6.7) 当指定flag时`--j2objc_dead_code_removal`，入口类的列表将被传递收集并用作入口点来执行死代码分析。然后将从最终的 ObjC 应用程序包中删除未使用的类。 |
| `jre_deps`      | `List of labels; optional``j2objc_library`此规则 翻译的所有 Java 代码所需的附加 JRE 仿真库的列表 。默认情况下，仅链接核心 JRE 功能。 |

## objc_import

```
objc_import(name, hdrs, alwayslink, archives, compatible_with, deprecation, distribs, features, includes, licenses, restricted_to, sdk_dylibs, sdk_frameworks, sdk_includes, tags, target_compatible_with, testonly, textual_hdrs, visibility, weak_sdk_frameworks)
```

`.a`该规则以文件的形式封装了一个已经编译好的静态库 。它还允许使用受支持的相同属性导出标头和资源`objc_library`。

### 参数

| 属性                  |                                                              |
| :-------------------- | ------------------------------------------------------------ |
| `name`                | `Name; required`此目标的唯一名称。                           |
| `hdrs`                | `List of labels; optional`由该库发布的 C、C++、Objective-C 和 Objective-C++ 头文件的列表，将被源包含在相关规则中。这些标头描述了库的公共接口，并且可以通过源包含在此规则或相关规则中。不应由该库的客户端包含的标头应列在 srcs 属性中。如果启用了模块，这些将与源代码分开编译。 |
| `alwayslink`          | `Boolean; optional; default is False`如果为 1，任何依赖（直接或间接）此库的包或二进制文件都将链接到 `srcs`和中列出的文件的所有目标文件`non_arc_srcs`，即使其中一些不包含二进制文件引用的符号。如果您的代码没有被二进制代码显式调用，这很有用，例如，如果您的代码注册以接收某些服务提供的某些回调。 |
| `archives`            | `List of labels; required``.a`提供给依赖此目标的 Objective-C 目标 的文件列表。 |
| `includes`            | `List of strings; optional``#include/#import`要添加到此目标和所有依赖目标 的搜索路径列表。`#import/#include`这是为了支持未在其语句 中指定整个工作区路径的第三方和开源库 。路径是相对于包目录解释的，除了实际的客户端根目录外，还包括 genfiles 和 bin 根目录（例如`bazel-genfiles/pkg/includedir` 和）。`bazel-out/pkg/includedir`与[COPTS](https://docs.bazel.build/versions/main/be/objective-c.html#objc_library.copts)不同，这些标志是为该规则和依赖它的每个规则添加的。（注意：不是它所依赖的规则！）要非常小心，因为这可能会产生深远的影响。如有疑问，请将“-iquote”标志添加到[COPTS](https://docs.bazel.build/versions/main/be/objective-c.html#objc_library.copts)。 |
| `sdk_dylibs`          | `List of strings; optional`要链接的 SDK .dylib 库的名称。例如，“libz”或“libarchive”。如果二进制文件在其依赖关系树中包含任何 C++ 或 Objective-C++ 源代码，则会自动包含“libc++”。链接二进制文件时，将使用在该二进制文件的传递依赖图中命名的所有库。 |
| `sdk_frameworks`      | `List of strings; optional`要链接的 SDK 框架的名称（例如“AddressBook”、“QuartzCore”）。在为 iOS、tvOS 和 watchOS 平台构建时，总是包含“UIKit”和“Foundation”。对于 macOS，始终只包含“Foundation”。链接顶级二进制文件（例如 apple_binary）时，该二进制文件的传递依赖图中列出的所有 SDK 框架都会被链接。 |
| `sdk_includes`        | `List of strings; optional``#include/#import`要添加到此目标和所有依赖目标 的搜索路径列表，其中每个路径都相对于`$(SDKROOT)/usr/include`. |
| `textual_hdrs`        | `List of labels; optional`此规则中的源文件或此库的用户作为标头包含的 C、C++、Objective-C 和 Objective-C++ 文件的列表。与 hdrs 不同，这些不会与源代码分开编译。 |
| `weak_sdk_frameworks` | `List of strings; optional`要弱链接的 SDK 框架的名称。例如，“媒体可访问性”。与定期链接的 SDK 框架不同，如果来自弱链接框架的符号在运行时不存在，则它们不会导致错误。 |

## objc_library

```
objc_library(name, deps, srcs, data, hdrs, alwayslink, compatible_with, copts, defines, deprecation, distribs, enable_modules, exec_compatible_with, exec_properties, features, includes, licenses, linkopts, module_map, module_name, non_arc_srcs, pch, restricted_to, runtime_deps, sdk_dylibs, sdk_frameworks, sdk_includes, tags, target_compatible_with, testonly, textual_hdrs, toolchains, visibility, weak_sdk_frameworks)
```

此规则从给定的 Objective-C 源文件生成一个静态库。

### 参数

| 属性                  |                                                              |
| :-------------------- | ------------------------------------------------------------ |
| `name`                | `Name; required`此目标的唯一名称。                           |
| `deps`                | `List of labels; optional`链接在一起形成最终捆绑包的目标列表。 |
| `srcs`                | `List of labels; optional`为创建库目标。这些是您签入的文件，以及任何生成的文件。使用 Clang 将源文件编译成 .o 文件。此目标的 srcs 属性中的任何源或标头都可以包含/导入头文件，但 hdrs 中的标头或依赖此规则的任何目标都不能包含/导入头文件。此外，预编译的 .o 文件可以作为 srcs 给出。请注意确保提供的 .o 文件的架构与构建的架构保持一致，以避免丢失符号链接器错误。 |
| `hdrs`                | `List of labels; optional`由该库发布的 C、C++、Objective-C 和 Objective-C++ 头文件的列表，将被源包含在相关规则中。这些标头描述了库的公共接口，并且可以通过源包含在此规则或相关规则中。不应由该库的客户端包含的标头应列在 srcs 属性中。如果启用了模块，这些将与源代码分开编译。 |
| `alwayslink`          | `Boolean; optional; default is False`如果为 1，任何依赖（直接或间接）此库的包或二进制文件都将链接到 `srcs`和中列出的文件的所有目标文件`non_arc_srcs`，即使其中一些不包含二进制文件引用的符号。如果您的代码没有被二进制代码显式调用，这很有用，例如，如果您的代码注册以接收某些服务提供的某些回调。 |
| `copts`               | `List of strings; optional`传递给编译器的额外标志。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。这些标志仅适用于该目标，而不适用于它所依赖的对象或依赖于它的对象。请注意，对于生成的 Xcode 项目，在 copts 中使用“-I”标志指定的目录路径被解析出来，如果它们是相对路径，则在前面加上“$(WORKSPACE_ROOT)/”，并添加到相关 Xcode 目标的标头搜索路径中. |
| `defines`             | `List of strings; optional``-D`传递给编译器的 额外标志。它们应该采用形式`KEY=VALUE`或简单的形式，`KEY`并且不仅传递给该目标的编译器（按原样`copts` ），而且还传递给该目标的所有`objc_`依赖项。受制于[“制作变量”](https://docs.bazel.build/versions/main/be/make-variables.html)替换和 [Bourne shell 标记化](https://docs.bazel.build/versions/main/be/common-definitions.html#sh-tokenization)。 |
| `enable_modules`      | `Boolean; optional; default is False`启用 clang 模块支持（通过 -fmodules）。将此设置为 1 将允许您 @import 系统标头和其他目标：@import UIKit; @import path_to_package_target; |
| `includes`            | `List of strings; optional``#include/#import`要添加到此目标和所有依赖目标 的搜索路径列表。`#import/#include`这是为了支持未在其语句 中指定整个工作区路径的第三方和开源库 。路径是相对于包目录解释的，除了实际的客户端根目录外，还包括 genfiles 和 bin 根目录（例如`bazel-genfiles/pkg/includedir` 和）。`bazel-out/pkg/includedir`与[COPTS](https://docs.bazel.build/versions/main/be/objective-c.html#objc_library.copts)不同，这些标志是为该规则和依赖它的每个规则添加的。（注意：不是它所依赖的规则！）要非常小心，因为这可能会产生深远的影响。如有疑问，请将“-iquote”标志添加到[COPTS](https://docs.bazel.build/versions/main/be/objective-c.html#objc_library.copts)。 |
| `linkopts`            | `List of strings; optional`传递给链接器的额外标志。          |
| `module_map`          | `Label; optional`此目标的自定义 Clang 模块映射。不鼓励使用自定义模块映射。大多数用户应该使用 Bazel 生成的模块映射。如果指定，Bazel 将不会为此目标生成模块映射，但会将提供的模块映射传递给编译器。 |
| `module_name`         | `String; optional`设置此目标的模块名称。默认情况下，模块名称是目标路径，所有特殊符号都替换为_，例如 //foo/baz:bar 可以导入为 foo_baz_bar。 |
| `non_arc_srcs`        | `List of labels; optional`为创建不使用 ARC 的库目标而处理的 Objective-C 文件列表。此属性中的文件的处理方式与 srcs 属性中的文件非常相似，但编译时未启用 ARC。 |
| `pch`                 | `Label; optional`头文件添加到每个正在编译的源文件（弧和非弧）。在 BUILD 文件中不鼓励使用 pch 文件，这应该被视为已弃用。由于 pch 文件实际上并未预编译，因此这不是构建速度增强，而只是一个全局依赖项。从构建效率的角度来看，您实际上更好地将您需要的内容直接包含在您需要的源代码中。 |
| `runtime_deps`        | `List of labels; optional`在运行时延迟加载的框架目标列表。它们包含在应用程序包中，但在构建时未链接。 |
| `sdk_dylibs`          | `List of strings; optional`要链接的 SDK .dylib 库的名称。例如，“libz”或“libarchive”。如果二进制文件在其依赖关系树中包含任何 C++ 或 Objective-C++ 源代码，则会自动包含“libc++”。链接二进制文件时，将使用在该二进制文件的传递依赖图中命名的所有库。 |
| `sdk_frameworks`      | `List of strings; optional`要链接的 SDK 框架的名称（例如“AddressBook”、“QuartzCore”）。在为 iOS、tvOS 和 watchOS 平台构建时，总是包含“UIKit”和“Foundation”。对于 macOS，始终只包含“Foundation”。链接顶级二进制文件（例如 apple_binary）时，该二进制文件的传递依赖图中列出的所有 SDK 框架都会被链接。 |
| `sdk_includes`        | `List of strings; optional``#include/#import`要添加到此目标和所有依赖目标 的搜索路径列表，其中每个路径都相对于`$(SDKROOT)/usr/include`. |
| `textual_hdrs`        | `List of labels; optional`此规则中的源文件或此库的用户作为标头包含的 C、C++、Objective-C 和 Objective-C++ 文件的列表。与 hdrs 不同，这些不会与源代码分开编译。 |
| `weak_sdk_frameworks` | `List of strings; optional`要弱链接的 SDK 框架的名称。例如，“媒体可访问性”。与定期链接的 SDK 框架不同，如果来自弱链接框架的符号在运行时不存在，则它们不会导致错误。 |

## available_xcodes

```
available_xcodes(name, default, deprecation, distribs, features, licenses, tags, testonly, versions, visibility)
```

规则实例可以依赖此规则的两个目标`xcode_config`来指示远程和本地可用的 xcode 版本。这允许从集体可用的 xcode 中选择官方 xcode 版本。

### 参数

| 属性       |                                                              |
| :--------- | ------------------------------------------------------------ |
| `name`     | `Name; required`此目标的唯一名称。                           |
| `default`  | `Label; required; nonconfigurable`此平台的默认 xcode 版本。  |
| `versions` | `List of labels; optional; nonconfigurable`此平台上可用的 xcode 版本。 |

## xcode_config

```
xcode_config(name, default, deprecation, distribs, features, licenses, local_versions, remote_versions, tags, testonly, versions, visibility)
```

`--xcode_version_config`构建标志可以引用此规则的单个目标，以将`--xcode_version`标志转换为可接受的官方 xcode 版本。这允许从许多注册别名中选择官方 xcode 版本。

### 参数

| 属性              |                                                              |
| :---------------- | ------------------------------------------------------------ |
| `name`            | `Name; required`此目标的唯一名称。                           |
| `default`         | `Label; optional; nonconfigurable`默认使用的 xcode 官方版本。如果未指定构建标志，则使用提供的`xcode_version`目标指定的版本。`xcode_version`如果 `versions`设置了，这是必需的。如果设置`remote_versions`或 设置，则可能不`local_versions`设置。 |
| `local_versions`  | `Label; optional; nonconfigurable`这`xcode_version targets that are available locally. These are used along with local_versions to select a mutually available version. This may not be set if versions is set.` |
| `remote_versions` | `Label; optional; nonconfigurable`这`xcode_version targets that are available remotely. These are used along with remote_versions to select a mutually available version. This may not be set if versions is set.` |
| `versions`        | `List of labels; optional; nonconfigurable`公认`xcode_version targets that may be used. If the value of the xcode_version build flag matches one of the aliases or version number of any of the given xcode_version targets, the matching target will be used. This may not be set if remote_versions or local_versions is set.` |

## xcode_version

```
xcode_version(name, default_ios_sdk_version, default_macos_sdk_version, default_tvos_sdk_version, default_watchos_sdk_version, deprecation, distribs, features, licenses, tags, testonly, version, visibility)
```

表示具有该 xcode 版本可接受别名的单个官方 xcode 版本。见`xcode_config`规则。

### 参数

| 属性                          |                                                              |
| :---------------------------- | ------------------------------------------------------------ |
| `name`                        | `Name; required`此目标的唯一名称。                           |
| `default_ios_sdk_version`     | `String; optional; nonconfigurable`使用此版本的 xcode 时默认使用的 ios sdk 版本。`ios_sdk_version`构建标志将覆盖此处指定的值 。 |
| `default_macos_sdk_version`   | `String; optional; nonconfigurable`使用此版本的 xcode 时默认使用的 macosx sdk 版本。`macos_sdk_version`构建标志将覆盖此处指定的值 。 |
| `default_tvos_sdk_version`    | `String; optional; nonconfigurable`使用此版本的 xcode 时默认使用的 tvos sdk 版本。`tvos_sdk_version`构建标志将覆盖此处指定的值 。 |
| `default_watchos_sdk_version` | `String; optional; nonconfigurable`使用此版本的 xcode 时默认使用的 watchos sdk 版本。`watchos_sdk_version`构建标志将覆盖此处指定的值 。 |
| `version`                     | `String; required; nonconfigurable`Xcode 的一个版本的正式版本号。 |



# shell规则

## 规则

- [sh_binary](https://docs.bazel.build/versions/main/be/shell.html#sh_binary)
- [sh_library](https://docs.bazel.build/versions/main/be/shell.html#sh_library)
- [sh_test](https://docs.bazel.build/versions/main/be/shell.html#sh_test)

## sh_binary

```
sh_binary(name, deps, srcs, data, args, compatible_with, deprecation, distribs, env, exec_compatible_with, exec_properties, features, licenses, output_licenses, restricted_to, tags, target_compatible_with, testonly, toolchains, visibility)
```

该`sh_binary`规则用于声明可执行的 Bourne shell 脚本。（`sh_binary`用词不当：它的输出不一定是二进制文件。）此规则确保所有依赖项都已构建，并`runfiles`在执行时出现在该区域中。我们建议您`sh_binary()`在脚本名称减去扩展名后命名您的规则（例如`.sh`）；规则名称和文件名必须不同。

#### 例子

对于没有依赖项和一些数据文件的简单 shell 脚本：

```
sh_binary(
    name = "foo",
    srcs = ["foo.sh"],
    data = glob(["datafiles/*.txt"]),
)
```

### 参数

| 属性   |                                                              |
| :----- | ------------------------------------------------------------ |
| `name` | `Name; required`此目标的唯一名称。                           |
| `deps` | `List of labels; optional`要聚合到此目标中的“库”目标列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common.deps)`deps` 的属性的一般评论。此属性应用于列出其他`sh_library`提供解释程序源代码的规则，这些规则取决于`srcs`. 这些规则提供的文件将出现在`runfiles`该目标的文件中。 |
| `srcs` | `List of labels; required`包含 shell 脚本的文件。该属性必须是一个单例列表，其元素是 shell 脚本。该脚本必须是可执行的，并且可以是源文件或生成的文件。运行时所需的所有其他文件（无论是脚本还是数据）都属于该 `data`属性。 |

## sh_library

```
sh_library(name, deps, srcs, data, compatible_with, deprecation, distribs, exec_compatible_with, exec_properties, features, licenses, restricted_to, tags, target_compatible_with, testonly, visibility)
```

此规则的主要用途是将一个逻辑“库”聚合在一起，该逻辑“库”由相关脚本（不需要编译或链接的解释语言程序，例如 Bourne shell）以及这些程序在运行时需要的任何数据组成。然后可以`data`根据一个或多个`sh_binary`规则的属性使用此类“库”。

您可以使用该[`filegroup`](https://docs.bazel.build/versions/main/be/general.html#filegroup)规则来聚合数据文件。

在解释型编程语言中，“代码”和“数据”之间并不总是有明显的区别：毕竟，从解释器的角度来看，程序只是“数据”。出于这个原因，该规则具有三个本质上等价的属性 `srcs`：`deps`和`data`。当前的实现不区分这些列表的元素。所有三个属性都接受规则、源文件和生成的文件。然而，将属性用于其通常目的（与其他规则一样）是一种很好的做法。

#### 例子

```
sh_library(
    name = "foo",
    data = [
        ":foo_service_script",  # an sh_binary with srcs
        ":deploy_foo",  # another sh_binary with srcs
    ],
)
```

### 参数

| 属性   |                                                              |
| :----- | ------------------------------------------------------------ |
| `name` | `Name; required`此目标的唯一名称。                           |
| `deps` | `List of labels; optional`要聚合到此目标中的“库”目标列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common.deps)`deps` 的属性的一般评论。此属性应用于列出其他`sh_library`提供解释程序源代码的规则，这些规则取决于`srcs`. 这些规则提供的文件将出现在`runfiles`该目标的文件中。 |
| `srcs` | `List of labels; optional`输入文件列表。此属性应用于列出属于此库的 shell 脚本源文件。脚本可以使用 shell 的`source` 或`.`命令加载其他脚本。 |

## sh_test

```
sh_test(name, deps, srcs, data, args, compatible_with, deprecation, distribs, env, env_inherit, exec_compatible_with, exec_properties, features, flaky, licenses, local, restricted_to, shard_count, size, tags, target_compatible_with, testonly, timeout, toolchains, visibility)
```

规则创建一个`sh_test()`编写为 Bourne shell 脚本的测试。

查看[ 所有测试规则共有的属性 (*_test)](https://docs.bazel.build/versions/main/be/common-definitions.html#common-attributes-tests)。

#### 例子

```
sh_test(
    name = "foo_integration_test",
    size = "small",
    srcs = ["foo_integration_test.sh"],
    deps = [":foo_sh_lib"],
    data = glob(["testdata/*.txt"]),
)
```

### 参数

| 属性   |                                                              |
| :----- | ------------------------------------------------------------ |
| `name` | `Name; required`此目标的唯一名称。                           |
| `deps` | `List of labels; optional`要聚合到此目标中的“库”目标列表。[请参阅关于所有构建规则共有 ](https://docs.bazel.build/versions/main/be/common-definitions.html#common.deps)`deps` 的属性的一般评论。此属性应用于列出其他`sh_library`提供解释程序源代码的规则，这些规则取决于`srcs`. 这些规则提供的文件将出现在`runfiles`该目标的文件中。 |
| `srcs` | `List of labels; required`包含 shell 脚本的文件。该属性必须是一个单例列表，其元素是 shell 脚本。该脚本必须是可执行的，并且可以是源文件或生成的文件。运行时所需的所有其他文件（无论是脚本还是数据）都属于该 `data`属性。 |
