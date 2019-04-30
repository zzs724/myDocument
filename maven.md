# Maven

## 一、什么是Maven

Maven项目对象模型(POM)，可以通过一小段描述信息来管理项目的构建，报告和文档的项目管理工具软件

管理项目的工具

## 二、Maven的生命周期

清除、编译、测试、打包、安装、部署

**（1）clean 清理自动生成的文件，也就是target目录**

**（2）Validate 验证Maven描述文件是否有效**

**（3）Compile 编译java代码**

**（4）Test 运行测试代码**

**（5）Package 项目打成war包**

**（6）Verify 验证构件包是否有效**

**（7）Install 将构件包安装到本地仓库**

**（8）Site 生成项目站点**

**（9）Deploy 将构件包部署到远程仓库**

## 三、常用命令

#### 	1、创建Maven普通Java项目

```xml
            mvn archetype:create
                -DgroupId=packageName
                -DartifactId=projectName
```

#### 	2、创建Maven的Web项目

```xml
            mvn archetype:create
                -DgroupId=packageName
                -DartifactId=webappName
                -DarchetypeArtifactId=maven-archetype-webapp
```

#### 	3、反向生成 Maven 项目的骨架

```xml
 			mvn archetype:generate
```

#### 	4、编译源代码

​			--src/main/java目录java源码编译生成class （target目录下）

```xml
			mvn compile
```

#### 	5、编译测试代码

​			--src/test/java 目录编译

```xml
			mvn test-compile
```

#### 	6、运行测试

```xml
			mvn test
```

#### 	7、产生site

```xml
			mvn site
```

#### 	8、打包

​			--生成压缩文件：java项目#jar包；web项目#war包，也是放在target目录下

```xml
			mvn package
```

#### 	9、清除产生的项目

​			--删除target目录，也就是将class文件等删除

```xml
			mvn clean
```

#### 	10、在本地仓库安装jar/war

​			--将压缩文件(jar或者war)上传到本地仓库

```xml
			mvn install
```

#### 	11、只生成jar包

```xml
			mvn jar：jar
```

#### 	12、上传到私服

```xml
			mvn deploy
```

#### 	13、验证项目是否正确，所需资源是否可用

```xml
			mvn validate
```

#### 	14、运行任何检查

```xml
			mvn verify
```

