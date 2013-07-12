# OnBuild readme

 Msbuild targets library install/uninstall via NuGet.

## OnBuild.PackageAssemblyForNuget

 Packaging Assembly for NuGet.

PM> Install-Package OnBuild.PackageAssemblyForNuget 

Build the project.

+ you got Error "Nuspec file created please edit it"

 add nuspec to project and edit and build.

+ if you got Error "The replacement token 'author' has no value."

  edit Properties/AssemblyInfo.cs AssemblyCompany attribute.

+ if you got Error "The replacement token 'description' has no value."

  edit Properties/AssemblyInfo.cs AssemblyDescription attribute.

+ if you got Warning bellow edit nuspec for resolve.

  Issue: Remove sample nuspec values.

  Description: The value "http://PROJECT_URL_HERE_OR_DELETE_THIS_LINE" for ProjectUrl is a sample value and should be removed.

  Description: The value "http://LICENSE_URL_HERE_OR_DELETE_THIS_LINE" for LicenseUrl is a sample value and should be removed.

  Description: The value "http://ICON_URL_HERE_OR_DELETE_THIS_LINE" for IconUrl is a sample value and should be removed.	

  Description: The value "Tag1 Tag2" for Tags is a sample value and should be removed.

  Description: The value "Summary of changes made in this release of the package." for ReleaseNotes is a sample value and should be removed.


## OnBuild.PublishNugetPackage

 Publishing NuGet package to NuGet server or file system repository.

PM> Install-Package OnBuild.PublishNugetPackage

- How to Configure publishing to NuGet repository

 create file YOURPROJECTNAME.csproj.nupublish as publish settings.

	`<?xml version="1.0" encoding="utf-8" ?>`
	`<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >`
	`	<PropertyGroup>`
	`	<DoNuGetPublish Condition="'$(Configuration)|$(Platform)' == 'Release|AnyCPU'" >true</DoNuGetPublish>`
	`		<PublishRunsAfter>PackageAssemblyForNuget</PublishRunsAfter>`
	`		<NuGetPublishTargetIsFileSystemSource>true</NuGetPublishTargetIsFileSystemSource>`
	`		<NuGetPublishTarget>D:\LocalRepos</NuGetPublishTarget>`
	`	</PropertyGroup>`
	`</Project>`

DoNuGetPublish : boolean, default is false, when if true executes publish,
  in sample configure. build configuration is Release|AnyCPU to publish.

PublishRunsAfter : string, default is "Build", publish runs on after configured target name.

  if you combined OnBuild.PackageAssemblyForNuget,
   PublishRunsAfter set to PackageAssemblyForNuget.

NuGetPublishTargetIsFileSystemSource : boolean, default is true, 
 when true, NuGetPublishTarget required filesystem path.
 when false, NuGetPublishTarget required NuGet server location.

NuGetPublishTarget : string, no default value.
 target path to NuGet repository.


- Configure API key to NuGet server

 please read [NuGet documentation](http://docs.nuget.org/docs/creating-packages/creating-and-publishing-a-package#api-key).

 

