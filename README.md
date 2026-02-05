# 3D BUG Algorithm for Multi-Floor Path Planning
This repository contains the MATLAB code for the paper "BUG-FIRE: A 3D Path Planning Algorithm with Augmented Reality Integration for Firefighter Navigation in Unknown Multi-Floor Buildings," published in the Fire Technology Journal. You can find the paper [here]().

## Abstract
Path planning in unknown, multi-floor buildings presents significant challenges for both autonomous systems and human navigation. Navigating such environments requires reaching a target location without prior knowledge of the building’s layout or obstacles. In particular, firefighters face these challenges during emergencies, where low-visibility conditions and restricted movement complicate navigation. This paper introduces BUG-FIRE, a 3D path planning algorithm designed to assist firefighter navigation in single-tower buildings without prior environmental knowledge. BUG-FIRE combines BUG2, an algorithm widely used in autonomous robotic systems, and adapts it for first responder navigation, using it for intra-floor movement. For inter-floor transitions, we integrate an emergency exit exploration algorithm that ensures goal convergence while complying with building code standards, such as mandatory stairwell connectivity and emergency signage. We validate BUG-FIRE through 250 Monte Carlo simulations in a virtual building model, demonstrating a 100\% success rate within the tested simulation scenarios for reaching randomly selected targets across multiple floors. The results show that agents with a 30-meter vision radius reduce path length by 28.2\ compared to those with only 0.5-meter visibility, highlighting the importance of environmental perception. To bridge the gap to real-world applications, we implement a YOLOv8-based vision system on the Magic Leap 2 AR headset, enabling real-time emergency signage recognition and dynamic AR guidance. Experimental results indicate that users can successfully navigate 3D paths utilizing AR guidance, with trajectory lengths closely matching simulated benchmarks.

## Concept
This repository presents a novel 3D BUG algorithm designed for autonomous navigation in unknown multi-floor indoor environments, with a specific focus on assisting firefighters. The algorithm addresses the unique challenges of three-dimensional path planning in complex building structures where prior map information is unavailable. This implementation guarantees convergence for pedestrian agents or robots navigating to complex goals within multi-story buildings. While the resulting paths may not be optimal due to the absence of prior map information, the algorithm ensures that a viable path to the target is always found, regardless of the building's layout complexity.

The algorithm combines the classic BUG2 algorithm for planar route planning and a custom algorithm to find multi-floor paths to reach the goal floor which then we can implement BUG2. This adapted to work in three-dimensional spaces with multiple floors.

## Algorithm Features

- **3D Path Planning**: Navigate through unknown multi-story buildings with complex floor layouts.
- **Obstacle Avoidance**: Efficiently maneuver around obstacles on each floor.
- **Floor Transitions**: Seamlessly plan paths that involve changing floors via staircases or elevators.
- **Monte Carlo Simulation**: Includes a robust testing framework to evaluate algorithm performance across various scenarios.
- **Visualization**: 3D plotting capabilities to visualize the environment, obstacles, and planned paths.

## Environment

The algorithm is designed and tested in a simulated environment (with Matlab) based on the Engineering Gateway building at the University of California, Irvine (UCI). The environment includes:

- Multiple floors (2nd, 3rd, and 4th floors)
- Complex room layouts and corridors
- Obstacles and impassable areas
- Inter-floor connections (staircases/elevators)

## Usage

* Clone this repository
* Download Peter's Coke [repository](https://petercorke.com/toolboxes/robotics-toolbox/). The 2D BUG algorithm function and some navigation functions are used from this library.

## Monte Carlo Simulation

The repository includes a Monte Carlo simulation framework to test the algorithm's performance:

- Generates random start and goal points across different floors.
- Runs multiple iterations to assess success rate, path length, and execution time.
- Provides statistical analysis of the results.

## Visualization

The code includes 3D visualization tools to:

- Display the multi-floor environment.
- Show obstacles and floor layouts.
- Illustrate planned paths and algorithm execution.

## Results

The simulations allow us to play with two different parameters radius vision of the robot and the width of the vision cone of the robot. The simulations result in a 100% convergence in all tested scenarios. This way proposing an indoor algorithm that guarantees a path to the goal even though the initial information is just the start and final coordinates. No pre-map information is known by the agent.


## How to Cite
If you use this work, please cite the following paper:
> **BUG-FIRE: A 3D Path Planning Algorithm with Augmented Reality Integration for Firefighter Navigation in Unknown Multi-Floor Buildings**<br>
> E. Sangenis, and A. M. Shkel<br>
> *Fire Technology*, accepted, doi:0.1007/s10694-026-01872-9, 2026.

**BibTeX:**

```bibtex
@ARTICLE{bugFireSangenis,
  author={Sangenis, Eudald and Andrei M. Shkel},
  journal={Fire Technology}, 
  title={BUG-FIRE: A 3D Path Planning Algorithm with Augmented Reality Integration for Firefighter Navigation in Unknown Multi-Floor Buildings}, 
  year={2026},
  volume={xx},
  number={x},
  pages={xx-xx},
  doi={10.1007/s10694-026-01872-9}
}
```

## Authorship
Eudald Sangenis (esangeni@uci.edu)
