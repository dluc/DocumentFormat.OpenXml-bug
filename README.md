Feature request: https://github.com/ClosedXML/ClosedXML/issues/2315

Edit Solution.csproj to see the different behavior:

# Error using DocumentFormat.OpenXml 3.0.2

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <OutputType>Exe</OutputType>
        <TargetFramework>net8.0</TargetFramework>
        <ImplicitUsings>enable</ImplicitUsings>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="ClosedXML" Version="0.102.2"/>
        <PackageReference Include="DocumentFormat.OpenXml" Version="3.0.2"/>
    </ItemGroup>
</Project>
```

Output:
```
Unhandled exception. System.MissingMethodException: Method not found: 'DocumentFormat.OpenXml.OpenXmlElementList DocumentFormat.OpenXml.OpenXmlElement.get_ChildElements()'.
   at ClosedXML.Excel.XLWorkbook.LoadSpreadsheetDocument(SpreadsheetDocument dSpreadsheet)
   at ClosedXML.Excel.XLWorkbook.LoadSheets(Stream stream)
   at ClosedXML.Excel.XLWorkbook.Load(Stream stream)
   at ClosedXML.Excel.XLWorkbook..ctor(Stream stream, LoadOptions loadOptions)
   at ClosedXML.Excel.XLWorkbook..ctor(Stream stream)
   at Solution.Program.Main() in Program.cs:line 9
```

# Success using DocumentFormat.OpenXml 2.20.0

```xml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <OutputType>Exe</OutputType>
        <TargetFramework>net8.0</TargetFramework>
        <ImplicitUsings>enable</ImplicitUsings>
    </PropertyGroup>
    <ItemGroup>
        <PackageReference Include="ClosedXML" Version="0.102.2"/>
        <PackageReference Include="DocumentFormat.OpenXml" Version="2.20.0"/>
    </ItemGroup>
</Project>
```

Output:
```
Success
```
