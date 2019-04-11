# buildscript

## publish to bintray

### 1. 在需要发布的build.gradle文件内追加如下配置

``` groovy
ext {
    groupId = 'groupId'
    artifactId = 'artifactId'
    versionName = 'versionName'
    versionDescribe = 'version describe' // 版本描述

    licenses = [ 'Apache-2.0' ] // 仓库创建时选择的license, 不能随便写
    websiteUrl = 'website' // 项目网址
    issueUrl = 'issue url' // issue地址
    vcsUrl = 'git url' // 项目仓库地址
    labels = ['label1', 'label2'] // 项目标签
    describe = 'describe' // 项目描述
}
apply from: 'https://raw.githubusercontent.com/YakinBlog/buildscript/master/publish_bintray.gradle'
```

### 2. 运行shell脚本发布，内部会自动执行assembleRelease、javadocJar、sourcesJar、generatePomFileForLibraryPublication打包

``` shell
./gradlew bintrayUpload
``` 