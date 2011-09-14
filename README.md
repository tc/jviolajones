# JViolaJones
http://code.google.com/p/jviolajones/

## Description
This package is a Java implementation of the Viola-Jones algorithm, able to load OpenCV XML files.

It can be used to detect either faces or any objects you have learned a cascade classifier from.

However, this project does not implement the learning part of the Viola-Jones algorithm (you still have to learn examples with OpenCV tools).

## Update
I just added the Canny Prunning algorithm, as in OpenCV, to identify regions unlikely to contain faces and speed up detection.

As I've seen some of you have downloaded the jar, I'd like to know if you found it useful (and if it did work !). Why not raise an issue telling what you think about it ?

## Use
The runnable jar available in the Downloads section should be called this way :

java -jar jviolajones2.jar imageFileName OpenCVXmlFile
(Some cascade files, as well as a test image, can be downloaded from the Downloads section.)

If you want to integrate this package in your code, this should work :

```
import detection.Detector;

String fileName="yourfile.jpg";
Detector detector=new Detector("haarcascade_frontalface_default.xml");
List<Rectangle> res=detector.getFaces(fileName, 2, 1.25f, 0.1f,3,true);
If you don't detect enough faces (or too much), please adjust the Parameters.
```

