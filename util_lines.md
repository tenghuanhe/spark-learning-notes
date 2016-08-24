#Spark中一些有用的lines
* 打印某一个partition中的所有元素

```
rdd.mapPartitionsWithIndex((index: Int, it: Iterator[Int]) => 
  it.toList.map(x =>
    if (index == 0)
      {println(x)})
      .iterator).collect
```

* Setting up Intellij Projects for Spark

```
mkdir my-project
mkdir -p my-project/src/main/scala
mkdir -p my-project/src/test/scala
mkdir -p my-project/project
```
In the **project** directory, cat a new file called plugins.sbt with the following content
```
addSbtPlugin("com.github.mpeltonen" % "sbt-idea" % "1.6.0")
```

In the project root, create a file called build.sbt containing:
```
name := "Project Name"

version := "1.0"

scalaVersion := "2.10.4"

libraryDependencies += "org.apache.spark" %% "spark-core" % "1.5.1"
```

At the project root level, run the following
```
sbt update
sbt gen-idea
```
