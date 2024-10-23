# AChartEngine installation guide

## Installing Maven
1. Download Maven from the official website: https://maven.apache.org/download.cgi <br/>
2. Extract the downloaded archive to a directory on your system, for example: `C:\apache-maven-3.9.9` <br/>
3. Add the Maven `bin` directory to your system's PATH environment variable: <br/>
   - Add `C:\apache-maven-3.9.9\bin` to the system environment variables. <br/>
4. Verify the installation by running the following command in a terminal: <br/>
```mvn --version```

## Downloading AChartEngine
1. Clone the AChartEngine library repository: <br/>
   - Open a terminal, navigate to an any desired directory, and run: <br/>
```sh
git clone https://github.com/ddanny/achartengine.git
cd achartengine/achartengine
```
2. Open the `pom.xml` file (located in the `achartengine/achartengine` directory) in a text editor. <br/>
3. Find the following lines in the file: <br/>
```sh
<configuration>
    <source>1.6</source>
    <target>1.6</target>
</configuration>
```
4. Update the Java source and target version from `1.6` to `1.7`: <br/>
```sh
<configuration>
    <source>1.7</source>
    <target>1.7</target>
</configuration>
```

## Compiling AChartEngine
1. After modifying the `pom.xml` file, compile the library to generate a JAR file:<br/>
```sh
mvn package
```
2. Once the process completes, navigate to the `achartengine/achartengine/target` directory:<br/>
```sh
cd target
```
3. List the files in this directory by running:<br/>
```sh
ls
```
4. Look for the file `achartengine-1.2.0.jar`<br/>

## Adding AChartEngine to your Android Studio Project
1. Open your Android Studio project.<br/>
2. Switch to the `Project` view (instead of the default `Android` view) from the project hierarchy panel.<br/>
3. Right-click the `app` directory and create a new folder named `libs`.<br/>
4. Move the `achartengine-1.2.0.jar` file you generated earlier into the `libs` folder.<br/>
5. Open the `build.gradle.kts` file in the `app` folder.<br/>
6. In the `dependencies` block, add the following line to include the AChartEngine library:<br/>
```sh
dependencies {
    implementation(files("libs/achartengine-1.2.0.jar"))
}
```
7. Sync the Gradle project to apply the changes.<br/>

## Declaring the GraphicalActivity in the Manifest
Since you'll be using the GraphicalActivity class for rendering charts, you need to declare it in your Android manifest file.<br/>
1. Open the `AndroidManifest.xml` file.<br/>
2. Add the following activity declaration, replacing YOUR_PROJECT_NAME with the actual theme name of your project:<br/>
```sh
<activity
    android:name="org.achartengine.GraphicalActivity"
    android:theme="@style/Theme.YOUR_PROJECT_NAME" />
```


Once these steps are completed, you should be ready to start using AChartEngine in your project.
