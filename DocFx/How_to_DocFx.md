Tested with .NET 8.0

- New project > class library
- Create classes, methods and summaries
- Go to NuGet PackageManager and install docfx.console
- Rightclick solution and build it 
  -> there should be no errors or warnings
  -> after the build there should be a new directory in the tree --> _site
- open CLI and navigate to "project_directory/_site"
- run 'docfx serve .\'
- open http: //localhost:8080 in a browser (without whitespace)
