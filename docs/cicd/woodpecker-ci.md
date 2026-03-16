---
title: Woodpecker CI
---

Running on [Woodpecker CI](https://woodpecker-ci.org/) will use the standard theming for your build log output.

!!! info
    Please refer to the official [Woodpecker documentation](https://woodpecker-ci.org/docs/intro) for questions not covered here.

## Environment Variables

You can access [predefined environment variables](https://woodpecker-ci.org/docs/usage/environment#built-in-environment-variables) by using the `Bitbucket` class:

```csharp
WoodpeckerCI WoodpeckerCI => WoodpeckerCI.Instance;

Target Print => _ => _
    .Executes(() =>
    {
        Log.Information("Branch = {Branch}", WoodpeckerCI.CommitRef);
        Log.Information("Commit = {Commit}", WoodpeckerCI.CommitSha);
    });
```

A full reference of available variables and their documentation can be found [here](https://nuke.greemdev.net/docfx/api/Nuke.Common.CI.WoodpeckerCI.WoodpeckerCI.html).
