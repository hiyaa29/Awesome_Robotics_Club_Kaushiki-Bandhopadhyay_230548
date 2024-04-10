The program takes inputs from user to set the value for the initial position of the first joint. Then, it takes the joint angles of each line segment connecting two consecutive joints as inputs. 
The link lengths are given in the problem and are stored in a list.
If the sum of all link lengths( that is the total length of the arm is more than that of the distance between the first joint's initial position and target position, the target is unreachable.
This is followed by calculation of positions of the other joints using joint angles and link lengths.
After this, the position of the end effector( final joint) is set to be the same as target position and backward pass is carried out as per FABRIK algorithm, leading to movement of the entire arm.
This might cause the first joint to move from its initial position.
As the result, forward pass is carried out to make sure that the first joint does not move from its initial postion.
This forward and backard passes, together, constitute an iteration.
With each iteration, the end effector gets closer to the target and finally, converges.
However, it may also happen that it fails to converge to the target even after maximum number of allowed iterations. In that case, the program shows that the arm fails to converge.
Tolerance value is used to define the maximum permissible error between target location and end effector location at the time of convergence.
