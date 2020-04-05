# VsModDotnetTemplate
A template for dotnet new to create a new project/sln for VintageStoryMods

## Prerequirements:
 - dotnet-core >= 3.1 (https://dotnet.microsoft.com/download/dotnet-core)

## Install:
```
 $ dotnet install /path/to/nuget
```
## Usage:
1. It is recommended that you create the following environment variables otherwise you have to specify the path every time you use this template and your projects are coupled to the folder structure of your computer.
  - VINTAGE_STORY_DATA (e.g. C:\Users\YOURUSER\AppData\Roaming\VintagestoryData) and VINTAGE_STORY (e.g. c:/games/vintage_story) 
2. Install the template via dotnet install
3. To create a new solution:
```
 //directory where the solution should be residing (make sure the folder has the right name or use -n to specify one)
 $ dotnet new vsmodsln 
```
4. To create a new mod:
```
 //if you want to use the solution to start your mod, make sure you are in the mods directory of the solution
 //the directory where the mod should be residing (make sure the folder has the right name or use -n to specify one)
 $ dotnet new vsmod 
```

## Thanks:

  - https://github.com/copygirl for a good chunk of ideas and a basic process to create a mod template in dotnet-core
  - https://github.com/anegostudios/vsmodtemplate for the basic mod template and RedirectLogs.cs
