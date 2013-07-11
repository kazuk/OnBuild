# OnBuild readme

 Msbuild targets library install/uninstall via NuGet.

## OnBuild.PackageAssemblyForNuget

 Packaging Assembly for NuGet.

PM> Install-Package OnBuild.PackageAssemblyForNuget 

Build the project.

  you got Error "Nuspec file created please edit it"

 add nuspec to project and edit and build.

if you got Error "The replacement token 'author' has no value."

  edit Properties/AssemblyInfo.cs AssemblyCompany attribute.

if you got Error "The replacement token 'description' has no value."

  edit Properties/AssemblyInfo.cs AssemblyDescription attribute.

if you got Warning bellow edit nuspec for resolve.

  Issue: Remove sample nuspec values.

  Description: The value "http://PROJECT_URL_HERE_OR_DELETE_THIS_LINE" for ProjectUrl is a sample value and should be removed.

  Description: The value "http://LICENSE_URL_HERE_OR_DELETE_THIS_LINE" for LicenseUrl is a sample value and should be removed.

  Description: The value "http://ICON_URL_HERE_OR_DELETE_THIS_LINE" for IconUrl is a sample value and should be removed.	

  Description: The value "Tag1 Tag2" for Tags is a sample value and should be removed.

  Description: The value "Summary of changes made in this release of the package." for ReleaseNotes is a sample value and should be removed.

