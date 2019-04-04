## Setup Instructions

### Dependencies

This project involves the Simulator which can be downloaded [here](https://github.com/udacity/self-driving-car-sim/releases)

This repository includes two bash files (`install-mac.sh` and `install-ubuntu.sh`) that can be used to set up and install [uWebSocketIO](https://github.com/uWebSockets/uWebSockets) for either Linux or Mac systems. 

For windows you can use either Docker, VMware, or even [Windows 10 Bash on Ubuntu](https://www.howtogeek.com/249966/how-to-install-and-use-the-linux-bash-shell-on-windows-10/) to install uWebSocketIO. 
.

### Intalling Ipopt and CppAD

1.  Clone this repository and navigate to the cloned directory
2.  [Download](https://www.coin-or.org/download/source/Ipopt/) the appropriate version of Ipopt (3.12.7 or higher) from the link below.  You may also use wget or a similiar command to download the source from the command line (see Linux instructions).
3.  Follow the instructions for your environment

* [Ipopt](https://projects.coin-or.org/Ipopt)
  * **Mac:**
    ```
      brew tap brewsci/science
      brew install ipopt --with-openblas
    ```
    Alternatively, you may be able to install directly from this repository with the below, although you may be missing certain dependencies that need to be carried over from the above:
    ```
    brew tap udacity/CarND-MPC-Project https://github.com/udacity/CarND-MPC-Project
    brew install ipopt --with-openblas
    ```

 - **For Linux and Windows Ubuntu BASH** Please note that for any particular command, including execution of ```.sh``` scripts, it may be necessary to add ```sudo``` prior to the command.  It is also a good practice to run ```sudo apt-get update``` prior to installation of new libraries.

  * **Linux:**
    * ```sudo apt-get install gfortran```
    *  ```apt-get install unzip```
    * ```wget https://www.coin-or.org/download/source/Ipopt/Ipopt-3.12.7.zip && unzip Ipopt-3.12.7.zip && rm Ipopt-3.12.7.zip```
    * Call `install_ipopt.sh` with the source directory as the first argument, ex: ```./install_ipopt.sh Ipopt-3.12.7``` or ```bash install_ipopt.sh Ipopt-3.12.7```

  * **Windows:** For Windows environments there are two main options
    * Follow Linux instructions in the Ubuntu Bash environment. Please not that install instructions should be executed from the repository directory.  Changing to a Windows directory (ie ```cd /mnt/c .....```) can result in installation issues, particularly for Windows directories that contain spaces.
    * Use the docker container described [here](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/0949fca6-b379-42af-a919-ee50aa304e6a/lessons/f758c44c-5e40-4e01-93b5-1a82aa4e044f/concepts/16cf4a78-4fc7-49e1-8621-3450ca938b77), which comes pre-configured with Ipopt.
* [CppAD](https://www.coin-or.org/CppAD/)
  * Mac: `brew install cppad`
  * Linux `sudo apt-get install cppad` or equivalent.
  * **Windows:** For Windows environments there are two main options
    * Follow Linux instructions in the Ubuntu Bash environment
    * Use the docker container described [here](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/0949fca6-b379-42af-a919-ee50aa304e6a/lessons/f758c44c-5e40-4e01-93b5-1a82aa4e044f/concepts/16cf4a78-4fc7-49e1-8621-3450ca938b77), which comes pre-configured with CppAD.

### Troubleshooting

* If challenges to installation are encountered (install script fails).  Please consult the forums.  Please feel free to submit additional tips or forum threads to the [issue reports repo](https://github.com/udacity/sdc-issue-reports), for potential inclusion in this document.
*  **Some Mac users have experienced the following error:**
     ```
     Listening to port 4567
     Connected!!!
     mpc(4561,0x7ffff1eed3c0) malloc: *** error for object 0x7f911e007600: incorrect checksum for freed object
     - object was probably modified after being freed.
     *** set a breakpoint in malloc_error_break to debug
     ```
     This error has been resolved by updrading ipopt with
     ```brew upgrade ipopt --with-openblas```
     per this [forum post](https://discussions.udacity.com/t/incorrect-checksum-for-freed-object/313433/19)
