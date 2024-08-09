
# Rain-Runoff Modeling with Physics-Informed Neural Networks (PINN) and Quantum PINN (QPINN)

## Overview

This repository contains the implementation of two advanced computational approaches—**Physics-Informed Neural Networks (PINNs)** and **Quantum Physics-Informed Neural Networks (QPINNs)**—applied to a rain-runoff model. The rain-runoff process is crucial for hydrological modeling, predicting flood events, and managing water resources. By integrating physical laws into neural network training, PINNs aim to enhance model accuracy, while QPINNs seek to leverage quantum computing for improved performance in complex systems.

## Project Structure

- `rain_runoff_pinn.py`: Implementation of the rain-runoff model using Physics-Informed Neural Networks (PINNs).
- `rain_runoff_qpinn.py`: Implementation of the rain-runoff model using Quantum Physics-Informed Neural Networks (QPINNs).
- `data_generation.py`: Script for generating synthetic soil moisture data used for training the models.
- `README.md`: Project documentation.

## Model Overview

### Rain-Runoff Model: Mathematical Formulation

The rain-runoff process is modeled by a differential equation representing the rate of change of soil moisture \( S(t) \) over time:

\[
rac{dS}{dt} = P(t) - I(t) - ET(t) - R(S)
\]

where:
- \( S(t) \): Soil moisture at time \( t \).
- \( P(t) \): Precipitation rate.
- \( I(t) \): Infiltration rate (modeled using the Horton Infiltration Model).
- \( ET(t) \): Evapotranspiration rate (assumed constant).
- \( R(S) \): Runoff rate, dependent on soil moisture \( S \).

### Synthetic Data Generation

Synthetic soil moisture data over a 100-hour period is generated using the rain-runoff differential equation. The generated data is used as the target for training the models.

### Physics-Informed Neural Networks (PINN)

PINNs integrate the governing physical laws directly into the loss function to ensure that the network's predictions adhere to the underlying physics.

- **Network Architecture:**
  - **Input Layer:** Receives the time variable \( t \).
  - **Hidden Layers:** Consists of fully connected layers with activation functions.
  - **Output Layer:** Predicts soil moisture \( \hat{S}(t) \).

- **Loss Function:** 
\[
\mathcal{L}_{	ext{PINN}} = rac{1}{N} \sum_{i=1}^{N} \left( \hat{S}(t_i) - S_{	ext{true}}(t_i) 
\]

The loss function combines the data loss with a physics-based loss that penalizes deviations from the governing differential equation.

### Quantum Physics-Informed Neural Networks (QPINN)

QPINNs aim to leverage quantum computing to enhance the expressiveness of the model, particularly in scenarios where classical methods struggle with complexity.

- **Quantum Circuit:**
  - **Encoding Layer:** Encodes the input \( t \) into the quantum state using angle encoding.
  - **Variational Layer:** Applies a series of parameterized quantum gates to manipulate the quantum state.
  - **Measurement Layer:** Measures the qubits to obtain a classical output.

- **Hybrid Architecture:**
  - **Input Layer:** Receives the time variable \( t \).
  - **Classical Layer:** A classical neural network layer that pre-processes the input.
  - **Quantum Layer:** The quantum circuit, which processes the pre-processed input.
  - **Output Layer:** A classical neural network layer that processes the quantum circuit's output to predict soil moisture \( \hat{S}(t) \).

- **Loss Function:**
\[
\mathcal{L}_{	ext{QPINN}} = rac{1}{N} \sum_{i=1}^{N} \left( \hat{S}(t_i) - S_{	ext{true}}(t_i) 
\]

Focuses on minimizing the difference between predictions and true values.

## Results

The models were trained on the synthetic dataset, with the following key results:

### PINN
- **Final MSE:** 16.9948
- **Training Time:** 1.68 seconds

### QPINN
- **Final MSE:** 600.4258
- **Training Time:** 1914.86 seconds

### Analysis
- The PINN significantly outperformed the QPINN in accuracy and training efficiency.
- QPINN showed potential but requires further refinement in quantum circuit design and parameter optimization.

## Conclusion

This project explores the application of PINNs and QPINNs to a rain-runoff model, revealing the strengths and limitations of each approach. While PINNs demonstrate strong performance, QPINNs offer an intriguing quantum approach that warrants further exploration and development.

## Future Work

- **Enhance Quantum Circuit Expressivity:** Experiment with deeper quantum circuits and more qubits.
- **Incorporate Physics-Informed Loss in QPINNs:** Introduce the physics loss component in the QPINN training process.
- **Optimize Training Parameters:** Fine-tune learning rates and initialization strategies to improve convergence.

## Requirements

- Python 3.x
- PyTorch
- PennyLane
- NumPy
- Matplotlib

## How to Run

1. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
2. **Generate Data:**
   ```bash
   python data_generation.py
   ```
3. **Run PINN Model:**
   ```bash
   python rain_runoff_pinn.py
   ```
4. **Run QPINN Model:**
   ```bash
   python rain_runoff_qpinn.py
   ```

## License

This project is licensed under the MIT License.

## Contact

For questions or collaboration, please contact [Your Name] at [Your Email].