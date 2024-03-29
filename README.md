This project is cloned from the following directry and is adapted for the test tank developments in Nantes

https://github.com/TUDelft-DataDrivenControl/WaveFFControl


# WaveFFControl
Wave feedforward control input files for NREL 5MW on top of the OC3 floating platform in the above-rated region. So, only the blade pitch controller is included.

In order to run such files, you need the precompiled binaries from OpenFAST v3.0.0 in here [OpenFAST precompiled binaries](https://github.com/OpenFAST/openfast/releases) under Assets. The required binaries are: **openfast_x64.exe** and __OpenFAST-Simulink_x64.dll__

If you wish to run it with other OpenFAST versions, the corresponding input files should be used as well as the proper Simulink block corresponding to the version of interest.

This repository contains 2 simulink files:
1) **DISCON_NREL5MW_WaveFF.slx**: The file used to compile a DLL file on Windows, or an SO file on Linux, to be used either with OpenFAST or QBlade.
2) __OpenFAST_SFunc_NREL5MW_FF.slx__: An example of an OpenFAST model in Simulink.

### Steps to use the controller:
- In order to generate a DLL, the controller has to be initialized first. All you need to do is to open **"InitCompDISCON.m**, set the flag __'GenerateDLL'__ to true, then run the file. You should make sure that you have the latest 64-bit MATLAB version (tested with 2022a), and install the MinGW compiler:    (https://nl.mathworks.com/support/compilers.html)
- If you are interested in running the OpenFAST example in Simulink, first, you will need the input files to run OpenFAST, which are not provided here, but can be downloaded from OpenFAST github repository. Once the input files are set up, run **"Run_OpenLoop.m"** file.

For the time being, only the NREL5MW atop the OC3 floater FOWT is considered, however, an extension to the other turbines and floaters will be included in the future.

## Referencing
In the event of publication of work resulting from the use of the controller, proper referencing to this repository should be included. 
