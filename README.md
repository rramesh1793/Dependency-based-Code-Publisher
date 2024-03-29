
(Create a folder Proj3 and transfer all files and folders in the repo before executing run.bat)

Compile:
devenv CodeAnalyzerEx.sln /rebuild debug

Run:  
cd x64/Debug/TestExecutive.exe ..\..\..\Proj3 *.h *.cpp /f /r 


# Dependency-based-Code-Publisher

Purpose:
A Code Repository is a Program responsible for managing source code resources, e.g., files and documents. A fully developed Repository will support file persistence, management of versions, and the acquisition and publication of source and document files. This project focuses on just the publishing functionality of a repository.
In this project we will develop means to display source code files as web pages with embedded child links. Each link refers to a code file that the displayed code file depends on.

Things needed to develop this project.
* Each file to be published is a C++ source file. Our publisher will generate, for each of these, an HTML file, with most of the contents drawn from the code file.
* The pages we will generate have only static content, with the exception of some embedded JavaScript and styling, so we won't need a web server.
* We will need to preserve the white space structure of the displayed source code. That can be done embedding all the code between the tags < pre > and < / pre > or by using the CSS white-space property with value "pre" to style a div with all the code in its contents.
* Any markup characters in the code text will have to be escaped, e.g., replace < with &lt; and > with &gt;.
* File dependencies are displayed in the web page with embedded links, which are implemented in HTML5 with anchor elements: < a href ="[ url of referenced html page]" > source code file name < / a > 
* For each class, we will, optionally, implement outlining, similar to the visual studio outlining feature. To do that we will use the CSS display property, with values: normal or none, to control whether the contents of a div are visible or not.

The Code Publisher will be embedded in a mock Repository with almost no functionality except to support publishing of source code as web pages. Specifically you are not expected to provide support for:
* package checkin or checkout
* versioning

Features supported:
* Dependency analysis of the C++ source code files that are published using a dependency analyzer.
*  Ability to specify, on the command line, files to be published, by providing command line arguments for path and file patterns.
* Ability to display any file cited on the command line, by starting a process that runs a browser of our choice, naming the specification of the file we want to display.

Note that the CodePublisher project creates a code generator. Its inputs are C++ code and its outputs are HTML code.
