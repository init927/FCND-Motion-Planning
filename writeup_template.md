## Project: 3D Motion Planning

#### 1. Functionality of what's provided in `motion_planning.py` and `planning_utils.py`

`motion_planning.py` is basically where the code will de running to operate our drone in motion planning 

`planning_utils.py` provides additional functionalities to work with `motion_planning.py`. Some of the function such as A* , Collinearty check, Path Prunning etc.

### Implementing Your Path Planning Algorithm

#### 1. Set your global home position

To extract lat0,lon0 from csv file need to import csv and re library.
Re will help to fetch input and then split the values of alphabets and number. After that, convert string value into float.


#### 2. Set your current local position

It can be done using global_to_local fuction() from import through udacidrone.frame_utils.
`current_local_position = global_to_local(self.global_position, self.global_home)`

#### 3. Set grid start position from local position

`grid_start1=(int(current_local_position[0]-north_offset),int(current_local_position[1]-east_offset))`

This is done to achieve grid_Start position from local position

#### 4. Set grid goal position from geodetic coords

I have added Latitude and Longitude of Specific location while manully running drone on simulator.

#### 5. Modify A* to include diagonal motion (or replace A* altogether)

Adding sqrt(2) from math library to get the cost of diagonal movement is done as follows:
`NORTH_EAST = (-1,1,math.sqrt(2))`

#### 6. Cull waypoints

Path to Prune was added in planning_utils.py and then utilized in `motion_planning.py`

### Execute the flight
It works!
