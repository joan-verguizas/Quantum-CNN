# Quantum Convolutional Neural Network 

### Laboratory of Computational Physics (mode B) (2022-2023)

### Master's Degree: Physics of Data, University of Padova (IT) 

This project was developed as the final exam for the Laboratory of Computational Physics course during the 2022-2023 academic year. The work was carried out in a group during my first year in the Master's degree program in Physics of Data at the University of Padova. The aim of the project is to explore the application of Quantum Convolutional Neural Networks image recognition tasks using the MNIST dataset by comparing classical and quantum approaches to it. We investigate various quantum encoding strategies and examine how they impact the performance, efficiency, and accuracy of the QCNN models.

## Introduction to QCNN

Quantum Convolutional Neural Networks (QCNNs) leverage quantum computing's potential to enhance classical convolutional neural networks (CNNs). QCNNs utilize principles like superposition, entanglement, and quantum gates to process information more efficiently than classical models in specific contexts.

This project explores the quantum analog of classical CNNs, which incorporates concepts such as local connectivity and parameter sharing while utilizing quantum unitary operations in place of traditional filters and pooling layers. The QCNN’s key advantages lie in its potential ability to capture more complex patterns, thanks to quantum phenomena, with a more efficient encoding of information.

### Classical CNN vs QCNN

- Classical CNN: Utilizes shared weights, local connectivity, multiple feature maps, and pooling layers to perform tasks like image classification.
- QCNN: Operates similarly but replaces classical operations with quantum gates and measurements. It includes:
        - Quantum Convolutional Layers: Analogous to classical layers but using two-qubit unitary operations.
        - Quantum Pooling Layers: Reduces dimensionality through tracing out qubits, introducing nonlinearities in the process.

### Quantum Computing Background

- Quantum States: Represented as qubits, quantum information allows for more compact data representation through superposition and entanglement.
- Parametrized Quantum Circuits (PQC): These are the building blocks of quantum neural networks, where classical parameters control quantum gates. The model is optimized by minimizing a loss function using classical optimization methods (e.g., Adam optimizer).

## Encoding Techniques

Encoding classical data into quantum states is crucial for the performance of QCNNs. This project explored multiple encoding strategies:

- Basis Encoding: Simple and low-depth circuit, but susceptible to information loss due to data discretization.
- Angle Encoding: Encodes data into quantum states using rotation angles. Provides a continuous representation but leads to deeper circuits.
- Amplitude Encoding: Encodes information into the amplitude of quantum states, allowing for more compact representations of data, but introduces challenges with maintaining local connectivity.

### Basis Encoding

- Model Setup: 9 qubits were used for 3x3 input images with 30 parameters and a runtime of 21 seconds per epoch.
- Challenges: Limited accuracy due to discretization of input data.
- Results: A simple model with low computational depth but loss of information.

### Angle Encoding

- Model Setup: 9 qubits for 3x3 input images with 57 parameters, taking 40 seconds per epoch.
- Challenges: High circuit depth, which scales exponentially with the number of qubits.
- Results: Exponential scaling of encoded data with the number of qubits, though the model is susceptible to noise.

### Amplitude Encoding

- Model Setup (First Model): 6 qubits for 8x8 input images with 51 parameters and a runtime of 35 seconds per epoch.
- Challenges: The loss of local connectivity, requiring unitary block matrices to preserve it.
- Results: Improved data capacity but issues with local connectivity led to accuracy trade-offs.

## Hybrid Model

A hybrid approach combining classical and quantum layers was explored to achieve a better balance between efficiency and accuracy.

- Setup: 6 qubits were used for 8x8 input images with 168 parameters and a runtime of 45 seconds per epoch.
- Results: Improved accuracy compared to classical models, leveraging the quantum data capacity of amplitude encoding.

## Training and Results

Training Parameters:
    Training set size: 5000 samples
    Test set size: 500 samples
    Gradient descent optimizer: Adam
    Loss function: Mean Squared Error (MSE)
    Minibatch size: 75 samples
    Epochs: 50

Performance: The best results were achieved using the hybrid model with amplitude encoding, which showed a slight accuracy improvement over classical models while utilizing fewer parameters.

## Key Findings

- Quantum Advantages: QCNN models show potential in data capacity and accuracy improvements through quantum phenomena like amplitude encoding.
- Challenges: Quantum models face practical issues such as circuit depth and the complexity of preserving local connectivity.
- Encoding Strategy: Amplitude encoding proved to be the most effective for compact data representation but requires careful design to avoid locality problems.

## Conclusion

While fully leveraging quantum advantages remains challenging, this study shows the promise of QCNNs in handling more complex image recognition tasks, even with current technological limitations. The hybrid quantum-classical approach, especially with amplitude encoding, offers the most balanced and promising results for future research in this domain.
