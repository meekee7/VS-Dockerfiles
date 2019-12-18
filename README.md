Dockerfiles for installing running VS Build Tools in a Windows container

Note that creating the containers can take several hours, and these containers easily require 10GB+ of disk space.

Dockerfiles based on these tutorials by Microsoft:
* VS2017: https://docs.microsoft.com/en-us/visualstudio/install/build-tools-container?view=vs-2017
* VS2019: https://docs.microsoft.com/en-us/visualstudio/install/build-tools-container?view=vs-2019

If you want to adjust the installed workloads and packages, please refer to the package lists from Microsoft:
* VS2017: https://docs.microsoft.com/en-us/visualstudio/install/workload-component-id-vs-build-tools?vs-2017&view=vs-2017
* VS2019: https://docs.microsoft.com/en-us/visualstudio/install/workload-component-id-vs-build-tools?vs-2019&view=vs-2019

Full command line reference for the VS Installer:
* VS2017: https://docs.microsoft.com/en-us/visualstudio/install/use-command-line-parameters-to-install-visual-studio?view=vs-2017
* VS2019: https://docs.microsoft.com/en-us/visualstudio/install/use-command-line-parameters-to-install-visual-studio?view=vs-2019