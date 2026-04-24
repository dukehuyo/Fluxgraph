# Fluxgraph

## Description

Fluxgraph is a Python library designed for creating, visualizing, and analyzing directed graphs, particularly those representing workflows or processes. It provides a simple and intuitive API for defining nodes, edges, and their associated attributes, enabling users to model complex systems and gain insights through various graph algorithms and visualization techniques. Fluxgraph is ideal for tasks such as process optimization, dependency analysis, and task scheduling.

## Features

*   **Intuitive Graph Definition:** Easily create directed graphs using a clear and concise API.
*   **Node and Edge Attributes:** Associate arbitrary data with nodes and edges for detailed modeling.
*   **Graph Visualization:** Generate interactive and static graph visualizations using various layout algorithms. Supports integration with popular graphing libraries like NetworkX and Graphviz.
*   **Graph Algorithms:** Implement common graph algorithms such as topological sorting, shortest path finding, and cycle detection.
*   **Data Export/Import:** Serialize and deserialize graphs to and from various formats (e.g., JSON, CSV) for persistence and exchange.
*   **Customizable Styling:** Control the appearance of nodes and edges in visualizations through custom styling options.
*   **Filtering and Selection:**  Programmatically filter and select nodes and edges based on their attributes.
*   **Lightweight Dependencies:** Minimizes external dependencies for easy installation and deployment.
*   **Extensible Architecture:** Designed for easy extension with custom graph algorithms and visualization methods.
*   **Documentation and Examples:** Comprehensive documentation and practical examples to get you started quickly.

## Technologies Used

*   **Python 3.7+:** The primary programming language.
*   **NetworkX (Optional):** Used for advanced graph algorithms and visualization.  If installed, Fluxgraph will leverage it automatically.
*   **Graphviz (Optional):** Used for generating static graph visualizations. Requires Graphviz to be installed on the system.
*   **JSON:**  For graph serialization and deserialization.
*   **pytest:** For unit and integration testing.

## Installation

**Prerequisites:**

*   Python 3.7 or higher

**Using pip:**

```bash
pip install fluxgraph
```

**Optional Dependencies:**

For advanced features like graph visualization with NetworkX or Graphviz, you can install them as follows:

```bash
pip install fluxgraph[viz]  # Installs NetworkX and related packages
```

  Alternatively, install them individually:

```bash
pip install networkx
pip install graphviz  # Graphviz Python package (requires Graphviz system installation)
```

**Graphviz System Installation:**

*   **Linux:** `sudo apt-get install graphviz` or `sudo yum install graphviz` (depending on your distribution)
*   **macOS:** `brew install graphviz` (using Homebrew)
*   **Windows:** Download and install from the official Graphviz website (`https://graphviz.org/download/`) and add the Graphviz `bin` directory to your system's `PATH` environment variable.

**From source:**

1.  Clone the repository:

    ```bash
    git clone https://github.com/yourusername/fluxgraph.git
    cd fluxgraph
    ```

2.  Create a virtual environment (recommended):

    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Linux/macOS
    venv\Scripts\activate  # On Windows
    ```

3.  Install the dependencies:

    ```bash
    pip install -e .
    ```

**Running Tests:**

To run the unit tests, use pytest:

```bash
pytest
```

## Usage

```python
from fluxgraph import Graph

# Create a graph
graph = Graph()

# Add nodes
graph.add_node("A", label="Start")
graph.add_node("B", label="Process")
graph.add_node("C", label="End")

# Add edges
graph.add_edge("A", "B", weight=1)
graph.add_edge("B", "C", weight=2)

# Access node and edge attributes
graph.get_node("A").label  # Returns "Start"
graph.get_edge("A", "B").weight  # Returns 1

# Print graph information
print(graph)

# Example of visualizing the graph (requires NetworkX)
try:
    import networkx as nx
    import matplotlib.pyplot as plt

    nx_graph = graph.to_networkx()
    nx.draw(nx_graph, with_labels=True)
    plt.show()

except ImportError:
    print("NetworkX or Matplotlib not installed. Please install them to visualize the graph.")
```

See the `examples/` directory for more detailed examples.

## Contributing

We welcome contributions to Fluxgraph!  Please see the `CONTRIBUTING.md` file for guidelines on how to contribute.

## License

This project is licensed under the MIT License - see the `LICENSE` file for details.