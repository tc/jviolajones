# JViolaJones
http://code.google.com/p/jviolajones/

## Description
This package is a Java implementation of the Viola-Jones algorithm, able to load OpenCV XML files.

It can be used to detect either faces or any objects you have learned a cascade classifier from.

However, this project does not implement the learning part of the Viola-Jones algorithm (you still have to learn examples with OpenCV tools).

## Update
I just added the Canny Prunning algorithm, as in OpenCV, to identify regions unlikely to contain faces and speed up detection.

As I've seen some of you have downloaded the jar, I'd like to know if you found it useful (and if it did work !). Why not raise an issue telling what you think about it ?

## CLI app
Compile the code:

```
mvn assembly:assembly
```

Run an example, the first parameter is the image and the second is the
haar xml file.
```
java -jar target/jviolajones-1.0.2-jar-with-dependencies.jar src/test/resources/lena.jpg src/main/resources/haarcascade_frontalface_alt2.xml
```

## Use
If you want to integrate this package in your code, this should work :

```
import jviolajones.Detector;

String fileName="yourfile.jpg";
Detector detector=new Detector("haarcascade_frontalface_default.xml");
List<Rectangle> res=detector.getFaces(fileName, 2, 1.25f, 0.1f,3,true);
If you don't detect enough faces (or too much), please adjust the Parameters.
```

