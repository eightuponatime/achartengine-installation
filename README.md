# achartengine-installation

Need to install maven from https://maven.apache.org/download.cgi
Unpack inner folder to path "C:\apache-maven-3.9.9"
Add path "C:\apache-maven-3.9.9\bin" to system variables
Check installation by typing in the terminal
```mvn --version``` 

Then we need to install AChartEngine library to any place in our system.
Move to any prepared dir, than type:
```sh
git clone https://github.com/ddanny/achartengine.git
cd achartengine/achartengine
```
Then you need to open file pom.xml and find the lines:
```sh
<configuration>
	<source>1.6</source>
	<target>1.6</target>
</configuration>
```
Then you need to change source and target values to 1.7
```sh
<configuration>
	<source>1.7</source>
	<target>1.7</target>
</configuration>
```

then type a command to compile a library and generate a jar file
```sh
mvn package
```
then you can type 
```sh
cd target
```
then list all files with ls command and find achartengine-1.2.0.jar

now open your android studio project, move to build.gradle.kts and in the
dependencies block you need to add
```sh
dependencies {
  //noinspection GradlePath
  implementation(files("your_custom_path/achartengine/achartengine/target/achartengine-1.2.0.jar"))
}
```

than just sync gradle and you're ready to go!
