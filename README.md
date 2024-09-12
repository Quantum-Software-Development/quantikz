
# Quantikz: A Quantum Circuit Typesetting Tool for LaTeX

Welcome to the **Quantikz** tutorial repository! This project is designed to help you create elegant quantum circuit diagrams using LaTeX and the Quantikz package. In this repository, you'll find detailed instructions, example code, and 

## Introduction

**Quantikz** is a LaTeX package built on top of `TikZ`, specifically designed for typesetting quantum circuits. It offers a modern, simpler alternative to `QCircuit` and is highly customizable. Whether you're new to quantum computing or an experienced researcher, Quantikz allows you to create professional, publication-quality quantum circuits.

### Key Features

- **Quantum and Classical Wires**: Support for different wire types in a single circuit.
- **Customizable Gates**: Easily create common quantum gates (Hadamard, Pauli-X, etc.) and controlled operations.
- **Highlighting and Slicing**: Highlight parts of your circuit or slice it for step-by-step explanations.
- **Export Options**: Export diagrams to PDF, PNG, and other formats.


## Table of Contents

1. [Installation](#installation)
2. [Basic Usage](#basic-usage)
    - [Quantum Wires](#quantum-wires)
    - [Gates and Measurement](#gates-and-measurement)
    - [Controlled Gates](#controlled-gates)
    - [Labelling Circuits](#labelling-circuits)
3. [Exporting Diagrams](#exporting-diagrams)
4. [Commands and Options](#commands-and-options)
5. [Converting from QCircuit](#converting-from-qcircuit)
6. [Troubleshooting](#troubleshooting)
7. [Citation](#citation)
8. [License](#license)


## Installation

To use Quantikz, ensure that your LaTeX distribution includes the `Quantikz` package. Most current TeX distributions should have it available. In your LaTeX document, include the following in the preamble:

```latex
\usepackage{tikz}
\usetikzlibrary{quantikz2}
```

If you're uploading to arXiv, you may need to manually include the Quantikz file by adding tikzlibraryquantikz2.code.tex to your project.

Basic Usage
Quantum Wires
In Quantikz, quantum circuits are organized in a matrix-like format. Each column is separated by &, and new rows are created with \\. By default, all wires are quantum wires.

```latex
\begin{quantikz}
& \gate{H} & \ctrl{1} & \gate{X} & \meter{} \\
& \targ{}  & \ctrl{-1} & \gate{H} & \meter{}
\end{quantikz}
```

This creates a basic quantum circuit with Hadamard (H), controlled gate (ctrl), Pauli-X (X), and measurement gates.

Gates and Measurement
Use the \gate command to add gates. You can also add measurement gates (\meter) and phase gates (\phase):

```latex
\begin{quantikz}
& \gate{H} & \gate[2]{U} & \gate{R_Z(\theta)} & \meter{} \\
& & & \phase{\alpha} &
\end{quantikz}
Controlled Gates
For controlled gates, use the \ctrl and \targ commands. Here's an example of a controlled gate and a swap gate:
```

```latex
\begin{quantikz}
& \ctrl{1} & \targ{} & \swap{1} & \ctrl[vertical wire=c]{2} & \\
& \control{} & \ctrl[open]{-1} & \targX{} & \gate{X} & \\
&&&& \gate{U} & \meter{} \wire[u][1]{c}
\end{quantikz}
```

