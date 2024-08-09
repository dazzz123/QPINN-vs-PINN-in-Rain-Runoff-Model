# Rain-Runoff Modeling with PINN and QPINN

## Overview

This project explores the application of Physics-Informed Neural Networks (PINNs) and Quantum Physics-Informed Neural Networks (QPINNs) to model the rain-runoff process, which is vital for hydrological studies and flood prediction. The goal is to integrate physical laws directly into the training process (PINN) and leverage quantum computing techniques (QPINN) for enhanced performance.

## Key Features

- **Rain-Runoff Model**: Based on a differential equation that describes the change in soil moisture over time.
- **PINN Implementation**: A neural network trained to satisfy both data-driven and physics-informed loss functions.
- **QPINN Implementation**: A hybrid quantum-classical model that uses quantum circuits to potentially enhance the neural network’s capacity to model complex phenomena.

## Results

- **PINN**: Achieved a final Mean Squared Error (MSE) of 17.0180 with a training time of 1.68 seconds.
- **QPINN**: Achieved a final MSE of 600.4258 with a training time of 1914.86 seconds, indicating that further optimization is needed.

## Future Work

- Improve quantum circuit design in QPINN.
- Integrate physics-informed constraints directly into QPINNs.
- Optimize training parameters for better convergence.


## Contact

For questions or collaboration, please reach out to Soumyadip Das at soumyadipdas321@gmail.com.
