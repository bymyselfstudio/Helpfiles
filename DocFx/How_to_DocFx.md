Tested with .NET 8.0 in Visual Studio 2022 Community

### First init

- New project > class library (no .NET Framework! Has to be .NET 6.0 and higher!)
- Create classes, methods and summaries
- Go to NuGet PackageManager and install docfx.console
- Rightclick solution and build it (state of build can be seen in output console)
  * there should be no errors or warnings
  * after the build there should be a new directory in tree --> _site
- open CLI and navigate to "project_directory/_site"
- run 'docfx serve .\\'
- open http: //localhost:8080 in a browser (without whitespace)


### Updating existing documentation

WIP
