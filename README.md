# Swagger themes

[![github issues](https://img.shields.io/github/issues/oqo0/swagger-themes?&color=E0AF18)]()
[![github last commits](https://img.shields.io/github/last-commit/oqo0/swagger-themes)]()

Change Swagger documentation theme easily.

## Install
With NuGet CLI:
```
nuget install oqo0.SwaggerThemes
```
Using NuGet Package Manager:
https://www.nuget.org/packages/oqo0.SwaggerThemes/

## Usage
```csharp
app.UseSwagger();
app.UseSwaggerTheme(Theme.UniversalDark);
```

> [!WARNING]  
> Don't use `UseSwaggerUI()` before `UseSwaggerTheme()` or themes are not going to get installed.

#### Adding custom CSS
```csharp
string customCss = "body {" +
                   "    background-color: red;" +
                   "}";

app.UseSwaggerTheme(Theme.UniversalDark, customCss );
```

## Themes
#### Dracula
![alt text](assets/dracula.png)
```csharp
app.UseSwaggerTheme(Theme.Dracula);
```

#### Monokai
![alt text](assets/monokai.png)
```csharp
app.UseSwaggerTheme(Theme.Monokai);
```

#### One Dark
![alt text](assets/one-dark.png)
```csharp
app.UseSwaggerTheme(Theme.OneDark);
```

#### Universal Dark
![alt text](assets/universal-dark.png)
```csharp
app.UseSwaggerTheme(Theme.UniversalDark);
```

#### X-Code Light
![alt text](assets/x-code-light.png)
```csharp
app.UseSwaggerTheme(Theme.XCodeLight);
```

#### Nord Dark
```csharp
app.UseSwaggerTheme(Theme.NordDark);
```

## Creating your own themes

1. Create theme `.css` in `Themes` directory.
2. Add a placeholder for filename in `Theme.cs`:
```csharp
public static Theme YourTheme => new("your-theme.css");
```
3. Add an embedded resource for your `.css` file:
```xml
    ...
    <EmbeddedResource Include="Themes\your-theme.css" />
</ItemGroup>
```
4. Use any other complete theme as a template.
5. Test your new theme:
```csharp
app.UseSwaggerTheme(Theme.YourTheme);
```