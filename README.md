# CarND-Controls-MPC
Self-Driving Car Engineer Nanodegree Program

A MPC optimizes the current controls while keeping future controls into account.




## Processing pipeline

1. Initialize mpc class
2. Collect data from simulator
3. Convert map space to car space
4. Fit line to get coefficients
5. Error calculation (Cross track and Psi) and state definition.
6. Solve (Computational Infastructure for Operations Research library)
7. Pass output to simulator
8. Predicted line visual for simulator
9. Way point visual for simulator
10.Add latency to mimic real world driving conditions

## The model

### Latency

### Comparison to PID controller

integration of speed and steering angle
can handle straight line performance better
better recovery , I found once the PID controller gets "off track" it sometimes doesn't seem to be able to get back ontrack, where as since MPC re-calculates the cost continually it felt better for this.
imagine better for more complex problems, as it would appear you can arbitrarily add items to the cost function

as a sub component of this better model, one example is accounting for latency


### Hyperparamters


## Further research and opportunities

Further tuning
Magic functions() like solve / COIN library
Some of the concepts behind transformations
Code refactoring, all 3 functions God functions, there has got to be a better way to keep those vector indexes straight

## Sources and credits

This is a student project with the primary goal being to learn and understand the concepts behind a model predictive controller.

1. Udacity provided starter code, quiz code, and lessons.
2. Ideas from other students and mentors through forums, chat channel, and github.
3. The various dependency libraries.
4. [Wikipedia](https://en.wikipedia.org/wiki/Model_predictive_control)


---

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets) == 0.14, but the master branch will probably work just fine
  * Follow the instructions in the [uWebSockets README](https://github.com/uWebSockets/uWebSockets/blob/master/README.md) to get setup for your platform. You can download the zip of the appropriate version from the [releases page](https://github.com/uWebSockets/uWebSockets/releases). Here's a link to the [v0.14 zip](https://github.com/uWebSockets/uWebSockets/archive/v0.14.0.zip).
  * If you have MacOS and have [Homebrew](https://brew.sh/) installed you can just run the ./install-mac.sh script to install this.
* [Ipopt](https://projects.coin-or.org/Ipopt)
  * Mac: `brew install ipopt --with-openblas`
  * Linux
    * You will need a version of Ipopt 3.12.1 or higher. The version available through `apt-get` is 3.11.x. If you can get that version to work great but if not there's a script `install_ipopt.sh` that will install Ipopt. You just need to download the source from the Ipopt [releases page](https://www.coin-or.org/download/source/Ipopt/) or the [Github releases](https://github.com/coin-or/Ipopt/releases) page.
    * Then call `install_ipopt.sh` with the source directory as the first argument, ex: `bash install_ipopt.sh Ipopt-3.12.1`. 
  * Windows: TODO. If you can use the Linux subsystem and follow the Linux instructions.
* [CppAD](https://www.coin-or.org/CppAD/)
  * Mac: `brew install cppad`
  * Linux `sudo apt-get install cppad` or equivalent.
  * Windows: TODO. If you can use the Linux subsystem and follow the Linux instructions.
* [Eigen](http://eigen.tuxfamily.org/index.php?title=Main_Page). This is already part of the repo so you shouldn't have to worry about it.
* Simulator. You can download these from the [releases tab](https://github.com/udacity/CarND-MPC-Project/releases).

## Basic Build Instructions


1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./mpc`.

