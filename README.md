# MSBuild.Microsoft.VisualStudio.Tools.Office.targets

MSBuild targets for OfficeTools that come with Visual Studio. Useful for build servers that do not have Visual Studio installed.

Includes `.targets` files from Visual Studio 2017 that can be found in the `C:\Program Files (x86)\Microsoft Visual Studio\2017\{edition}\MSBuild\Microsoft\VisualStudio\v15.0\OfficeTools` directories.

The files are in the `tools\VSToolsPath` directory.

## Install

### NuGet

Package name is `Microsoft.VisualStudio.Tools.Office.targets`
https://www.nuget.org/packages/MSBuild.Microsoft.VisualStudio.Tools.Office.targets

## Use

Just install the NuGet package. The package automatically sets the `$(VSToolsPath)` property to use the targets file in the tools folder.

Or include the `.targets` files in your `.csproj`

```xml
<Import Project="$(VSToolsPath)\OfficeTools\Microsoft.VisualStudio.Tools.Office.targets" Condition="'$(VSToolsPath)' != '' And Exists('$(VSToolsPath)\OfficeTools\Microsoft.VisualStudio.Tools.Office.targets')" />
<Import Project="$(SolutionDir)\packages\MSBuild.Microsoft.VisualStudio.Tools.Office.targets.15.0.1\tools\VSToolsPath\OfficeTools\Microsoft.VisualStudio.Tools.Office.targets" Condition="('$(VSToolsPath)' == '' Or !Exists('$(VSToolsPath)\OfficeTools\Microsoft.VisualStudio.Tools.Office.targets')) And Exists('$(SolutionDir)\packages\MSBuild.Microsoft.VisualStudio.Tools.Office.targets.15.0.1\tools\VSToolsPath\OfficeTools\Microsoft.VisualStudio.Tools.Office.targets')" />
```

## License

Copyright (C) Microsoft Corporation. All rights reserved.
