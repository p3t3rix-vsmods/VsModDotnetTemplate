# VsModDotnetTemplate
A template for dotnet new to create a new project/sln for VintageStoryMods

## Prerequirements:
 - dotnet-core >= 3.1 (https://dotnet.microsoft.com/download/dotnet-core)

## Install:
Install the template via dotnet 
```
dotnet new -i ./path/to/nuget/P3t3rix.VsModTemplate.X.X.X.nupkg
```
## Usage:
### 1. Setup environment variables
It is recommended that you create the following environment variables:
  - VINTAGE_STORY_DATA (e.g. C:\Users\YOURUSER\AppData\Roaming\VintagestoryData) 
  - VINTAGE_STORY (e.g. c:/games/vintage_story) 
otherwise you have to specify the path every time you use this template and your projects are coupled to the folder structure of your computer.
### 2. Create a new solution:
Go to the directory where the solution should be residing and execute:
```
 $ dotnet new vsmodsln 
```
### 3. a) To create a new compiled mod:
Go to the ./CompiledMods/MyMod directory and create your mod (or specify it via the -o parameter of dotnet new) via :
``` 
 $ dotnet new vsbinmod --mod-id mymodid
```
### 3. b) To create a new source mod:
Go to the ./SourceMods/MyMod directory (or specify it via the -o parameter of dotnet new) and create your mod via :
```
 $ dotnet new vssrcmod --mod-id mymodid
```

### 4. Add your Mod to the solution
Use either Visual studio or use the command line 
```
 $ dotnet sln add ./path/to/your.csproj
```

### 5. Start modding and have fun
Make sure you select the right startup project otherwise visual studio will not build your mod when starting VintageStory.

## Remarks
Currently this setup is primarily focused on Visual Studio user. If there is interest it could be expanded to VSCode etc.

## Technical Details

Basically this template does the following:

-Create basic folders and a modinfo.json

-Add references to the VintageStory dlls

-Create a post build step for compiled mods to copy the binary and the assets to the solutiondir/bin

-Create a launchSettings.json that start VintageStory with --addModPaths to direct it to the compile output

-Add the RedirectLogs mod to the solution for easier debugging



## Thanks:

  - https://github.com/copygirl for a good chunk of ideas and a basic process to create a mod template in dotnet-core
  - https://github.com/anegostudios/vsmodtemplate for the basic mod template and RedirectLogs.cs
