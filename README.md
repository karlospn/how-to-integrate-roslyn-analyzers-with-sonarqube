# How to integrate your Roslyn Analyzers with Sonarqube

This repository is tied to the post [How to integrate your Roslyn Analyzer with SonarQube](https://www.mytechramblings.com/posts/how-to-integrate-your-roslyn-analyzers-with-sonarqube) from my blog site.

It contains:
-  The ``/MyRoslynAnalyzer`` folder contains a Roslyn Analyzer project with a single rule. 
    - This project gets packaged and published to [nuget.org](https://www.nuget.org/) using a Github action found on the ``.github`` folder.
-  The ``/Demo.WebApi`` folder contains a .NET 7 API
    - This API has installed the ``MyRoslynAnalyzer`` NuGet package.
- The ``/integrations/as-a-sonarqube-folder`` folder contains  SonarQube plugin and a ``Dockerfile`` that creates a SonarQube image with the plugin installed on it.
    - The ``myroslynanalyzer-plugin-1.0.0.jar`` is a SonarQube plugin and it is the result of converting the ``MyRoslynAnalyzer`` NuGet package into a SonarQube plugin using the [RoslynSonarQubePluginGenerator](https://github.com/SonarSource/sonarqube-roslyn-sdk) tool.
