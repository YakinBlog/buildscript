# buildscript

## publish to bintray

### 1. 在需要发布的build.gradle文件内追加如下配置

``` groovy
ext {
    groupId = 'groupId'
    artifactId = 'artifactId'
    versionName = 'versionName'
    describe = 'describe'

    licenses = [ 'Apache-2.0' ] // 仓库创建时选择的license, 不能随便写
    websiteUrl = 'website' // 项目网址
    vcsUrl = 'git url' // 项目仓库地址
    labels = ['label1', 'label2'] // 项目标签
}
apply from: 'https://raw.githubusercontent.com/YakinBlog/buildscript/master/publish_bintray.gradle'
```

### 2. 运行shell脚本发布

``` shell
./gradlew assembleRelease bintrayUpload
``` 