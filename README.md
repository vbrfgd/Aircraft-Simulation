# Aircraft-Simulation

## Installation
This tutorial has only been tested for Linux environment. It will need to be updated in the future.

### Install Python, TensorFlow, JSBSim and Gym-JSBSim
1. Install Python:  
https://www.python.org/downloads/
2. Install TensorFlow:  
Do all of the steps in https://www.tensorflow.org/install/source
3. (Optional) Install Anaconda if you want to use Jupiter Notebook for graphs:  
https://docs.anaconda.com/anaconda/install/index.html
4. Install JSBSim:  
https://github.com/JSBSim-Team/jsbsim/releases/tag/v1.1.11
5. Install Gym-JSBSim:  
https://github.com/Gor-Ren/gym-jsbsim

### Install FlightGear Flight Simulator
1. Install the latest version of FlightGear Flight Simulator:  
https://www.flightgear.org/download/  
For ubuntu, in order to install the lastest version of FlightGear with terminal, enter:
```
~$ sudo add-apt-repository ppa:saiarcot895/flightgear
```
then
```
~$ sudo apt update
```
And finally
```
~$ sudo apt update
```
2. Open the application – Settings – Download scenery automatically.  
3. Install the aircraft with the Aircraft tab in the application. At the moment, Gym-JSBSim has the environment for three aircrafts:  
    • Cessna 172P – environment name: Cessna172P  
    • McDonnell Douglas F-15 Eagle – environment name: F15  
    • Airbus A320 – environment name: A320  
4. Check if the application is runnable from terminal with  
```
fgfs --version
```

### Executing the program
1. Create a virtual environment. Paste the file [ddpg-agent-jsbsim.py](ddpg-agent-jsbsim.py) inside gym-jsbsim folder. In a Python virtutal environment, the folder is located in ```venv/lib/python3.8/site-packages```.
2. Run ddpg-agent-jsbsim.py. Start with NoFG in the environment name, for example:  
```
env = gym.make('JSBSim-TurnHeadingControl-Cessna172P-SHAPING.STANDARD-NoFG-v0')
```
3. Visualize the plot with ```env.render(mode='human')```

### Executing the program with FlightGear visualization

1. Change the NoFG to FG in the environment name. The environment name above, for example, will become:  
```
env = gym.make('JSBSim-TurnHeadingControl-Cessna172P-SHAPING.STANDARD-FG-v0')
```
2. Change the line with ```env.render(mode='human')``` to ```env.render(mode='flightgear')```, or add the later line instead if you want to keep the former visualization. FlightGear should be launched after the code is executed.
