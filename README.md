# UnexpectedPrefix
Minimal repro for unexpected prefix style issue triggering IDE1006.

Reproduce the issue by cloning and then running:

```
dotnet build --no-incremental
```

This shows the warning at the command line:

```
warning IDE1006: Naming rule violation: Prefix 's_' is not expected (https://learn.microsoft.com/dotnet/fundamentals/code-analysis/style-rules/ide1006)
```

...when building with the .NET 9 SDK.

However, changing the project to .NET 8 and adding a global.json that pins to the .NET 8 SDK does not show this warning.

```json
{
  "sdk": {
    "version": "8.0.300"
  }
}
```