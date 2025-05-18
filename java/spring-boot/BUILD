load("@rules_java//java:defs.bzl", "java_library", "java_binary") 
load("@rules_spring//springboot:springboot.bzl", "springboot")
load("//rules:java_war.bzl", "java_war")

java_binary(
    name = "spring-boot-hello-world",
    srcs = glob(["src/main/java/**/*.java"]),
    main_class = "com.bmuschko.Application",
    deps = [
        "@maven//:org_springframework_boot_spring_boot",
        "@maven//:org_springframework_boot_spring_boot_starter_web",
        "@maven//:org_springframework_boot_spring_boot_autoconfigure",
        "@maven//:org_springframework_spring_web",
    ],
)


java_library(
    name = "app_lib",
    srcs = glob(["src/main/java/**/*.java"]),
    resources = glob(["src/main/resources/**"]),
    deps = [
        "@maven//:org_springframework_boot_spring_boot",
        "@maven//:org_springframework_boot_spring_boot_starter_web",
        "@maven//:org_springframework_boot_spring_boot_autoconfigure",
        "@maven//:org_springframework_spring_web",
    ],
)

springboot(
    name = "springboot_app",
    java_library = ":app_lib",
    boot_app_class = "com.bmuschko.Application",
    deps = [
        "@maven//:org_springframework_boot_spring_boot_starter_web",
    ],
)

java_war(
    name = "web-app",
    java_srcs = glob(["src/main/java/**/*.java"]),
    compression = True,
    deps = [
        "@maven//:org_springframework_boot_spring_boot",
        "@maven//:org_springframework_boot_spring_boot_starter_web",
        "@maven//:org_springframework_boot_spring_boot_autoconfigure",
        "@maven//:org_springframework_spring_web",
    ],
)