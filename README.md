# AChartEngine installation guide

## maven installation
Need to install maven from https://maven.apache.org/download.cgi

## maven unpacking
Unpack archived folder to path "C:\apache-maven-3.9.9" <br/>
Add path "C:\apache-maven-3.9.9\bin" to system variables <br/>
Check installation by typing in the terminal <br/>
```mvn --version``` 

## download AChartEngine
Then we need to install AChartEngine library to any place in our system. <br/>
Move to any prepared dir, than type: <br/>
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
Then you need to change source and target values to 1.7 <br/>
```sh
<configuration>
	<source>1.7</source>
	<target>1.7</target>
</configuration>
```

then type a command to compile a library and generate a jar file <br/>
```sh
mvn package
```
then you can type <br/>
```sh
cd target
```
then list all files with ls command and find achartengine-1.2.0.jar <br/>

now open your android studio project, <br/>
go from "Android" project hierarchy to "Project" hierarchy. <br/>
right click on "app" folder and create new directory "libs" <br/>
move your compiled "achartengine-1.2.0.jar" file to "libs" folder <br/>
then move to "build.gradle.kts" in your app folder. 
in the dependencies block you need to add <br/>
```sh
dependencies {
  //noinspection GradlePath
  implementation(files("libs/achartengine-1.2.0.jar"))
}
```

than just sync gradle and you're ready to go!<br/>

and because we will use a special activity for drawing graphics "org.achartengine.GraphicalActivity"
we need to declare it in the manifest. Don't forget to specify the name of the project
```sh
<activity
	android:name="org.achartengine.GraphicalActivity"
	android:theme="@style/Theme.YOUR_PROJECT_NAME" />
```
