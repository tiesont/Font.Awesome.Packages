# Font.Awesome.Packages

Repo for the Font.Awesome NuGet packages. **Please note that these packages and this repo are not part of the official Font Awesome project**. Use the Issues board here to report issues using any of these packages.

Packages are separated by type:

- [Font.Awesome](https://www.nuget.org/packages/Font.Awesome/) - your "standard" pre-compiled CSS version, plus the JavaScript shims.
- [Font.Awesome.Sass](https://www.nuget.org/packages/Font.Awesome.Sass/) - same font files, but with Sass source files. You will need to compile the Sass files as your project dictates.
- [Font.Awesome.Less](https://www.nuget.org/packages/Font.Awesome.Less/) - same font files, but with Less source files. You will need to compile the Less files as your project dictates.

All packages include Font Awesome **Free** icons - I suggest creating your own packages and hosting on [MyGet](https://www.myget.org/) or similar if you need Pro icons. I try to keep the package version number in-sync with the Font Awesome release version, when possible.

See https://fontawesome.com/how-to-use for help getting started, after you've added one of the above packages. I'll try to add some entries to the wiki here for suggestions for using the Sass and Less versions, at some point.

## Usage in ASP.NET Core or non ASP.NET projects

If you would like to use the packages in non full framework ASP.NET projects you'll have to add the following to your csproj file:

```xml
<ItemGroup>
  <PackageReference Include="Font.Awesome" Version="5.15.1" GeneratePathProperty="true" />	
  <None Include="$(PkgFont_Awesome)/Content/**/*" Link="%(RecursiveDir)%(Filename)%(Extension)" CopyToOutputDirectory="PreserveNewest" />
</ItemGroup>
```

This will copy all files from the `Content` folder of the NuGet package into the root of the output of your project. If would like to place
the output in a different directory then prepend the directory name to the value of the `Link` attribute.  
