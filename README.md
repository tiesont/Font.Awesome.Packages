# Font.Awesome.Packages

Repo for the Font.Awesome NuGet packages. **Please note that these packages and this repo are not part of the official Font Awesome project**. Use the Issues board here to report issues using any of these packages.

Packages are separated by type:

- [Font.Awesome](https://www.nuget.org/packages/Font.Awesome/) - your "standard" pre-compiled CSS version, plus the JavaScript shims.
- [Font.Awesome.Sass](https://www.nuget.org/packages/Font.Awesome.Sass/) - same font files, but with Sass source files. You will need to compile the Sass files as your project dictates.
- [Font.Awesome.Less](https://www.nuget.org/packages/Font.Awesome.Less/) - same font files, but with Less source files. You will need to compile the Less files as your project dictates.

All packages include Font Awesome **Free** icons - I suggest creating your own packages and hosting on [MyGet](https://www.myget.org/) or similar if you need Pro icons. I try to keep the package version number in-sync with the Font Awesome release version, when possible.

See https://fontawesome.com/how-to-use for help getting started, after you've added one of the above packages. I'll try to add some entries to the wiki here for suggestions for using the Sass and Less versions, at some point.

## Customizing where files are placed

If you would like to customize where the files of package are placed you can do so in your csproj file:

```xml
<ItemGroup>
  <PackageReference Include="Font.Awesome" Version="5.15.1" ExcludeAssets="all" GeneratePathProperty="true" />	
  <None Include="$(PkgFont_Awesome)/Content/**/*" Link="assets/%(RecursiveDir)%(Filename)%(Extension)" CopyToOutputDirectory="PreserveNewest" />
</ItemGroup>
```

The `Link` attribute of the `None` element indicates where the files will be placed. Change the directory name `assets` to whatever you would like.
