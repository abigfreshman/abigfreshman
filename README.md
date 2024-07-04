# Setup Instructions
This code needs to be run in the NVIDIA simulation platform isaac sim. Please refer to the [official documentation](https://docs.omniverse.nvidia.com/isaacsim/latest/installation/index.html) to 
download and install isaac sim. Run the Python script in standalone mode. In the demo, we use isaac sim 2023.1.1 <br>
#### Create a conda environment:<br>  
```conda create -n voxposer-env python=3.9```<br>
```conda activate voxposer-env```<br>
#### Install other dependencies:<br>
```pip install -r requirements.txt```<br>

# Running Demo  <br>
cd to the isaac sim file and run`./python.sh ./Voxposer_isaac/voxposer/main.py` to display the demo. You can see [Hellow World](https://docs.omniverse.nvidia.com/isaacsim/latest/core_api_tutorials/tutorial_core_hello_world.html)
to konw more about how to run a python script in isaac.<br>

# Code Structure <br>

#### Core to VoxPoser:<br>
```main.py```: Run for this demo<br>
```LMP.py```: Implementation of Language Model Programs (LMPs) that recursively generates code to decompose instructions and compose value maps for each sub-task.<br>
```interfaces.py```: Interface that provides necessary APIs for language models (i.e., LMPs) to operate in voxel space and to invoke motion planner.<br>
```planners```: Implementation of a greedy planner that plans a trajectory (represented as a series of waypoints) for an entity/movable given a value map.<br>
```controllers.py```: Given a waypoint for an entity/movable, the controller applies (a series of) robot actions to achieve the waypoint.
```dynamics_models.py```: Environment dynamics model for the case where entity/movable is an object or object part. This is used in controllers.py to perform MPC.
```prompts/isaac_sim```: Prompts used by the different Language Model Programs (LMPs) in VoxPoser.
