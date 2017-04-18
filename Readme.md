# FlurlRepro
1. NuGet Restore (msbuild FlurlRepro.sln /t:Restore)
2. Note that project.lock.json file points to netstandard version of Flurl.dll

This leads to missing method exceptions, crashes in FxCopCmd, compiler warnings about mismatched versions of System.Net.Http
If you change the project to target net452 (modify the csproj & project.json), then the project.lock.json will point to
the portable version of Flurl.dll, which works.