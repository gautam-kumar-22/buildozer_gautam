add from distutils.version import LooseVersion

Update on line no. 790:

__sdk_dir = self.android_sdk_dir
build_tools_versions = os.listdir(join(__sdk_dir, 'build-tools'))
build_tools_versions = sorted(build_tools_versions, key=LooseVersion)
build_tools_version = build_tools_versions[-1]
gradle_files = ["build.gradle", "gradle", "gradlew"]
is_gradle_build = any((exists(join(dist_dir, x)) for x in gradle_files)) and build_tools_version >= '25.0'
