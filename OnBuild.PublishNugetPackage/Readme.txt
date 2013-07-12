OnBuild.PublishNugetPackage readme
=================================

- How to Configure publishing to NuGet repository

 create file YOURPROJECTNAME.csproj.nupublish as publish settings.

- - - - - - - - - nupublish sample - - - - - - - 
<?xml version="1.0" encoding="utf-8" ?>
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >
  <PropertyGroup>
    <DoNuGetPublish Condition="'$(Configuration)|$(Platform)' == 'Release|AnyCPU'" >true</DoNuGetPublish>
    <PublishRunsAfter>PackageAssemblyForNuget</PublishRunsAfter>
    
    <NuGetPublishTargetIsFileSystemSource>true</NuGetPublishTargetIsFileSystemSource>
    <NuGetPublishTarget>D:\LocalRepos</NuGetPublishTarget>
  </PropertyGroup>
</Project>
- - - - - - - - -

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

 please read NuGet documentation.

 http://docs.nuget.org/docs/creating-packages/creating-and-publishing-a-package#api-key

