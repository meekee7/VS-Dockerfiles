# escape=`

# Use the latest Windows Server Core image with .NET Framework 4.8
FROM mcr.microsoft.com/dotnet/framework/runtime:4.8
#FROM microsoft/dotnet-framework:4.7.1

# Restore the default Windows shell for correct batch processing.
SHELL ["cmd", "/S", "/C"]

# Download the Build Tools bootstrapper.
ADD https://aka.ms/vs/16/release/vs_buildtools.exe C:\TEMP\vs_buildtools.exe

# Install Build Tools excluding workloads and components with known issues.
RUN C:\TEMP\vs_buildtools.exe --quiet --wait --norestart --nocache `
    --installPath C:\BuildTools `
    --add Microsoft.VisualStudio.Workload.VCTools `
    --includeRecommended `
    --includeOptional `
    --remove Microsoft.VisualStudio.Component.VC.v141.x86.x64 `
    --remove Microsoft.VisualStudio.Component.VC.140 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.17134 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.16299 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10240 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.10586 `
    --remove Microsoft.VisualStudio.Component.Windows10SDK.14393 `
    --remove Microsoft.VisualStudio.Component.Windows81SDK `
 || IF "%ERRORLEVEL%"=="3010" EXIT 0

# Start developer command prompt with any other commands specified.
ENTRYPOINT C:\BuildTools\Common7\Tools\VsDevCmd.bat &&

# Default to PowerShell if no other command specified.
CMD ["powershell.exe", "-NoLogo", "-ExecutionPolicy", "Bypass"]