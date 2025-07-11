# HRSim
A **H**igh-capacity **R**ide-sharing **Sim**ulator calibrated by real request datasets and road networks.

## Platform architecture

The platform mainly consists of six parts, i.e., control centre, environment, RTV system, evaluation system, action system, and post-process system. The **control centre** is designed to integrate all functions, while the **environment** initialises road networks and updates real-time traffic situations. In the **RTV system**, each vehicle is regarded as an agent with its attributes including the current on-vehicle passengers, the planned route, etc. Agents drive to pick up and deliver their scheduled passengers according to the assignment results given by the integer linear programming (ILP) in the **evaluation system**. Subsequently, agents’ movements and speeds, and passengers’ states are updated in the **action system**. Finally, all simulation results are visualised in a **post-process system**.

<div align="center">
    <img src="intro-images/Simulator_Architecture.jpg", width="600" alt><br>
    Architecture of HRSim
</div>

## Functional modules

<div align="center">
    <img src="intro-images/Architect.jpg", width="800" alt><br>
    Functional modules incorporated in HRSim
</div>

## Updating

- [x] Implement dispatching and repositioning algorithms for ride-sharing and ride-sourcing
- [x] Add traffic flow models to measure traffic congestion, speed, and carbon emissions
- [x] Implement 2D visualization
- [ ] Provide implementation for Reinforcement Learning algorithms
- [ ] Provide implementation for car-following models
- [ ] Provide implementation for highly realistic 3D visualization


## Setup
1. Install dependencies and libraries
``` bash
pip install -r requirements.txt
```
2. Download [Road Network](https://drive.google.com/file/d/1plVhAfyD0ZtiFEfIHL8HYrPuLczdtvH0/view?usp=share_link) into **data**



## Simulation

### Run the demo
```bash
python simulation.py --cfg ./config/test.yaml  --DrawResult True
```

### Simulation results
[![Demonstration for simulation results](https://res.cloudinary.com/marcomontalbano/image/upload/v1683018353/video_to_markdown/images/youtube--upBATpfreoI-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/upBATpfreoI "Demonstration for simulation results")



## Dispatching Algorithm
<div align="center">
    <img src="intro-images/DispatchingAlgorithm.jpg", width="700" alt><br>
</div>
**Dispatching Algorithm.** (a) Passengers are preassigned to vehicles within their matching areas; then (b) each vehicle will be potentially scheduled with multiple passengers. (c) The platform checks the shareability of each vehicle's potential passengers by planning the shortest routes and verifying pickup and detour time constraints, e.g., Passengers 1 and 2 can share Vehicle 1, but Passengers 2 and 3 cannot share Vehicle 2 due to the detour time constraint. (d) RTV-graph can be established to connect all potential trips (including one or more requests) to vehicles. (e) The optimal matching results are obtained via ILP. (f) Vehicles pick up and deliver passengers according to the matching results of (e) and the planned shortest routes of (c).



## References

```
@inproceedings{Chen2025HRSim,
  title={HRSim: An agent-based simulation platform for high-capacity ride-sharing services},
  author={Chen, Wang and Shi, Hongzheng and Ke, Jintao},
  booktitle={2015 IEEE Intelligent Transportation Systems Conference (ITSC)},
  year={2025},
  organization={IEEE}
}
```

```
@article{chen2025scaling,
  title={Scaling laws of dynamic high-capacity ride-sharing},
  author={Chen, Wang and Yang, Linchuan and Chen, Xiqun and Ke, Jintao},
  journal={Transportation Research Part C: Emerging Technologies},
  volume={174},
  pages={105064},
  year={2025},
  publisher={Elsevier}
}
```

```
@article{chen2024quantifying,
  title={Quantifying traffic emission reductions and traffic congestion alleviation from high-capacity ride-sharing},
  author={Chen, Wang and Ke, Jintao and Chen, Xiqun},
  journal={Transportmetrica B: Transport Dynamics},
  volume={12},
  number={1},
  pages={2423235},
  year={2024},
  publisher={Taylor \& Francis}
}
```

```
@article{chen2024development,
  title={Development dilemma of ride-sharing: Revenue or social welfare?},
  author={Chen, Wang and Huang, Guan and Ke, Jintao},
  journal={arXiv preprint arXiv:2412.08801},
  year={2024}
}
```
