# SolarPILOT - Solar Power tower Integrated Layout and Optimization Tool

The SolarPILOT Open Source Project repository contains the source code, tools, and instructions to build a desktop version of the National Renewable Energy Laboratory's SolarPILOT. SolarPILOT is a design, characterization, and optimization tool for concentrating solar power (CSP) tower plants. It is available through this repository as a standalone application with full functionality, and it is also included in several CSP tower models within NREL's System Advisor Model (SAM) in limited form. For more details about SolarPILOT's capabilities, see the SolarPILOT website at [https://www.nrel.gov/csp/solarpilot.html](https://www.nrel.gov/csp/solarpilot.html). For details on integration with SAM, see the SAM website at [sam.nrel.gov](https://sam.nrel.gov).

The desktop version of SolarPILOT for Windows or Linux builds from the following open source projects:

* [SolTrace](https://github.com/nrel/soltrace) is a general tool for Monte-Carlo ray tracing that allows optical characterization of a wide range of possible systems. The tool is used by SolarPILOT alongside the analytical Hermite polynomial expansion model to ensure model accuracy.

* [SSC](https://github.com/nrel/ssc) is a set of "compute modules" that simulate different kinds of power systems and financial structures. It can be run directly using the [SAM Software Development Kit](https://sam.nrel.gov/sdk). **If you are looking for the algorithms underlying the models, they are located in this repository.**

* [LK](https://github.com/nrel/lk) is a scripting language that is integrated into SAM and allows users to add functionality to the program.

* [wxWidgets](https://www.wxwidgets.org/) is a cross-platform graphical user interface platform used for SAM's user interface, and for the development tools included with SSC (SDKtool) and LK (LKscript). The current version of SAM uses wxWidgets 3.1.0.

* [WEX](https://github.com/nrel/wex) is a set of extensions to wxWidgets for custom user-interface elements used by SAM, and by LKscript and DView, which are integrated into SAM.

* [Google Test](https://github.com/google/googletest) is a C++ test framework that enables comprehensive unit-testing of software.  Contributions to the project will eventually be required to have associated unit tests written in this framework.

* This repository, **SolarPILOT**, provides the user interface to assign values to inputs of the computational modules, run the modules in the correct order, and display calculation results. It also includes tools for editing LK scripts, viewing field layout and receiver flux map data, and performing multi-dimensional system optimization.

# Quick Steps for Building SolarPILOT

For detailed build instructions see the [wiki](https://github.com/NREL/SolarPILOT/wiki), with specific instructions for:

  * [Windows](https://github.com/NREL/SolarPILOT/wiki/Windows-Build)
  * [Linux](https://github.com/NREL/SolarPILOT/wiki/Linux-Build)

These are the general quick steps you need to follow to set up your computer for developing SolarPILOT:

1. Set up your development tools:

    * Windows: Visual Studio 2017 Community or other editions available at https://www.visualstudio.com/.
    * Linux: g++ compiler available at http://www.cprogramming.com/g++.html or as part of the Linux distribution.

2. Download the wxWidgets 3.1.0 source code for your operating system from https://www.wxwidgets.org/downloads/.

3. Build wxWidgets.

5. In Windows, create the WXMSW3 environment variable on your computer to point to the wxWidgets installation folder, or Linux, create the dynamic link `/usr/<USERNAME>/local/bin/wx-config-3` to point to `/path/to/wxWidgets/bin/wx-config`.

6. As you did for wxWidgets, for each of the following projects, clone (download) the repository, build the project, and then (Windows only) create an environment variable pointing to the project folder. Build the projects in the following order, and assign the environment variable for each project before you build the next one:

<table>
<tr><th>Project</th><th>Repository URL</th><th>Windows Environment Variable</th></tr>
<tr><td>LK</td><td>https://github.com/NREL/lk</td><td>LKDIR</td></tr>
<tr><td>WEX</td><td>https://github.com/NREL/wex</td><td>WEXDIR</td></tr>
<tr><td>Google Test</td><td>https://github.com/google/googletest</td><td>GTEST</td></tr>
<tr><td>SSC</td><td>https://github.com/NREL/ssc</td><td>SSCDIR</td></tr>
<tr><td>SolTrace</td><td>https://github.com/NREL/SolTrace</td><td>CORETRACEDIR</td></tr>
<tr><td>SolarPILOT</td><td>https://github.com/NREL/SolarPILOT</td><td></td></tr>
</table>

# Contributing

If you would like to report an issue with SolarPILOT or make a feature request, please let us know by adding a new issue on the [issues page](https://github.com/NREL/SolarPILOT/issues).

If you would like to submit code to fix an issue or add a feature, you can use GitHub to do so. Please see [Contributing](CONTRIBUTING.md) for instructions.

# License

SolarPILOT's open source code is copyrighted by the Alliance for Sustainable Energy and licensed under a [mixed MIT and GPLv3 license](LICENSE.md). It allows for-profit and not-for-profit organizations to develop and redistribute software based on SolarPILOT under terms of an MIT license and requires that research entities including national laboratories, colleges and universities, and non-profit organizations make the source code of any redistribution publicly available under terms of a GPLv3 license.
