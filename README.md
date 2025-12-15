# Dyn-WNTR

**Dyn-WNTR** is an extension of the **WNTR** framework([here](https://github.com/USEPA/WNTR)), designed to enable **real-time** and **dynamic simulations** of **water distribution networks (WDNs)**. This version allows for the continuous updating of water network models based on real-time data, providing a flexible and interactive platform for optimization, predictive modeling, and system management.

### Key Features:
- **Real-time Simulation**: Unlike traditional simulators, Dyn-WNTR supports real-time updates, enabling continuous changes to valves, pumps, demands, and network components during the simulation.
- **Integration with IoT and Digital Twins**: Dyn-WNTR can integrate real-time IoT sensor data through technologies like LoRaWAN, improving the accuracy and adaptability of water network simulations. This makes it a suitable framework for use in **digital twins** of WDNs, allowing operators to optimize and predict network behavior in real-time.
- **Dynamic Control and Analysis**: Users can interact with the simulation, adjusting network parameters on the fly. This capability enables dynamic testing of various scenarios, improving decision-making and system resilience.
- **Machine Learning Integration**: Dyn-WNTR can work alongside machine learning models, using real-time data to improve predictions and system optimization.

### Benefits:
- **Optimized Resource Management**: By enabling dynamic control and feedback, Dyn-WNTR helps in managing water resources more efficiently, adjusting parameters like pressure, flow, and demand in real-time.
- **Improved System Resilience**: Real-time updates and adaptability ensure that the system can respond to operational changes and potential issues as they arise.

### Installation

To use **Dyn-WNTR**, you’ll need to clone this repo (anything useful is in the mwntr folder).

### Example: Real-time Simulation with Dynamic Control

```python
import mwntr

# Initialize the model and simulation
wn = wntr.network.WaterNetworkModel()
wn.add_reservoir('R1', base_head=100.0)
wn.add_junction('J1', base_demand=10.0)
wn.add_pipe('P1', start_node_name='R1', end_node_name='J1', length=100, diameter=0.3)

# Create a simulation object
sim = MWNTRInteractiveSimulator(wn)
sim.init_simulation()

# Modify the system dynamically
sim.start_leak('J1')  # Introduce a leak at J1
sim.step_sim()  # Run the simulation for one timestep
sim.stop_leak('J1')  # Stop the leak after one timestep
```

### Contribution

We welcome contributions to improve and expand the functionality of **Dyn-WNTR**. Feel free to fork the repository, submit issues, or open pull requests with new features or bug fixes. Contributions can help us make the platform more scalable, user-friendly, and adaptable to real-world applications.

### Future Work

1. **Integration with Machine Learning**:  
   We plan to integrate **reinforcement learning (RL)** models for optimizing system management decisions, such as valve control and demand adjustment.

2. **Expansion to Larger Networks**:  
   Additional work will focus on improving the scalability of **Dyn-WNTR**, ensuring it can efficiently simulate large-scale water distribution networks with real-time updates.

3. **Digital Twin Integration**:  
   The future direction includes expanding **Dyn-WNTR**'s ability to interface with real-world sensor data, enhancing the effectiveness of **digital twins** and predictive maintenance.

4. **Merge into WNTR official repository**
   The plan is to merge this fork into the original project to enhance the capabilities of WNTR itself.

### License

**Dyn-WNTR** is open-source and distributed under the [MIT License](LICENSE). 

if you use this work in your research, cite us as:
```latex
@inproceedings{dyn_wntr,
  title={Dyn-WNTR: Dynamic Network Adaptive Extension for Hydraulic Simulations with WNTR},
  author={Locatelli, Pierluigi and Cattai, Tiziana and Palumbo, Simone and Cuomo, Francesca},
  booktitle={2025 IFIP Networking Conference (IFIP Networking)},
  year={2025},
  organization={IEEE}
}
```
