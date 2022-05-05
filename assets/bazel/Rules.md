# Rules
Language-specific native rules

| Language        | Binary rules         | Library rules                                                                           | Test rules                                      | Other rules                                                        |
| --------------- | -------------------- | --------------------------------------------------------------------------------------- | ----------------------------------------------- | ------------------------------------------------------------------ |
| Android         | android_binary       | aar_import android_library                                                              | android_instrumentation_test android_local_test | android_device android_ndk_repository android_sdk_repository       |
| C / C++         | cc_binary            | cc_import cc_library cc_proto_library fdo_prefetch_hints fdo_profile propeller_optimize | cc_test                                         | cc_toolchain cc_toolchain_suite                                    |
| Java            | java_binary          | java_import java_library java_lite_proto_library java_proto_library                     | java_test                                       | java_package_configuration java_plugin java_runtime java_toolchain |
| Objective-C     | apple_static_library | j2objc_library objc_import objc_library                                                 |                                                 | available_xcodes xcode_config xcode_version                        |
| Protocol Buffer |                      | proto_lang_toolchain proto_library                                                      |
| Python          | py_binary            | py_library                                                                              | py_test                                         | py_runtime                                                         |
| Shell           | sh_binary            | sh_library                                                                              | sh_test                                         |

 Language-agnostic native rules

| Family        | Rules                                                                 |
| ------------- | --------------------------------------------------------------------- |
| Extra Actions | action_listener extra_action                                          |
| General       | alias config_setting filegroup genquery genrule test_suite            |
| Platform      | constraint_setting constraint_value platform toolchain toolchain_type |
| Workspace     | bind local_repository new_local_repository                            |

## C\C++ Rules
### Binary rules
#### cc_binary
##### function：
		cc_binary(name, deps, srcs, data, additional_linker_inputs, args, compatible_with, copts, defines, deprecation, distribs, env, exec_compatible_with, exec_properties, features, includes, licenses, linkopts, linkshared, linkstatic, local_defines, malloc, nocopts, output_licenses, restricted_to, stamp, tags, target_compatible_with, testonly, toolchains, visibility, win_def_file)
##### 用途：
		产生binary的rule
##### demo：
		hello-world依赖了hello-greet library
![image](https://user-images.githubusercontent.com/20507750/166909050-7c6d458d-d781-480c-a3f4-21bf8b358677.png)

##### 属性


