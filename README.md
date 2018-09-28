# FlyGo_WebDemo_SSM

文档地址：https://www.flygo520.com/docs/maven/maven-1am45p762eros

# SSM简单例子描述

使用Maven搭建完整的SSM项目，里面涉及到Maven web项目对包的依赖，Maven应用插件对资源文件的管理。

# SSM 搭建过程

1、右键`New` -> 选择`Project...`

![创建项目 步骤1](https://www.flygo520.com/uploads/maven/images/m_638f1b24969a3ea13141e3fe99ae3bc9_r.png#size=360x0)

2、选择 `Maven Project` -> 选择 `下一步`

![创建项目 步骤2](https://www.flygo520.com/uploads/maven/images/m_13308dbd630a31831c4738811141fdf6_r.png#size=360x0)

3、勾选`Create a simple project  (skip archetype selection)`-> 选择`下一步`

![创建项目 步骤3](https://www.flygo520.com/uploads/maven/images/m_fed3710f5cac4cfe7890998cd9e20375_r.png#size=360x0)

4、填写相关信息，特别注意，Web项目有且只能选择 `Packaging` 为 `war` 类型。

![创建项目 步骤4](https://www.flygo520.com/uploads/maven/images/m_8ce90583bac3478edac61bd2217eed55_r.png#size=360x0)

# 项目目录结构

重点关注配置文件的拷贝到编译的class中。

![项目目录结构](https://www.flygo520.com/uploads/maven/images/m_d1a827d003c4a3df9953a70f0f7b8208_r.png#size=240x0)

1. maven默认只把src/main/resources里面的非.java文件进行编译到classes中
2. 如果希望src/main/java下的文件也被编辑到classes中,在pom.xml需要配置相关插件

```bash
<build>
	<resources>
		<resource>
			<directory>src/main/java</directory>
			<includes>
				<include>**/*.xml</include>
			</includes>
		</resource>
		<resource>
			<directory>src/main/resources</directory>
			<includes>
				<include>**/*.xml</include>
				<include>**/*.properties</include>
			</includes>
		</resource>
	</resources>
</build>
```
如果配置了，编译器会把相关的配置文件编译到classes中

![编译后的相关配置文件](https://www.flygo520.com/uploads/maven/images/m_e59a3ec7f33fb40b30a96599bc58399c_r.png#size=240x0)

# 演示Demo源码地址

https://github.com/jxaufang168/FlyGo_WebDemo_SSM
