# Road Network Reachability Map - Warshall's Algorithm

This project visualizes a road network between cities (nodes) and uses **Warshall's Algorithm** to calculate the reachability between them. The app allows users to add cities and roads, compute reachability, and see connections between nodes in an interactive graph format.

## Features

- **Add Cities and Roads**: Allows users to add cities (nodes) and direct roads (edges) between them.
- **Compute Reachability**: Uses Warshall's Algorithm to check if any two cities are indirectly connected.
- **Interactive Graph**: Visual representation of the road network where cities and their connections are displayed. Reachable cities are highlighted.
- **Responsive Design**: Works well on both desktop and mobile devices.

## Tech Stack

- **JavaScript**: Core logic and functionality.
- **D3.js**: For creating and displaying an interactive graph.
- **HTML/CSS**: Basic structure and styling, including responsive design for mobile support.

## Project Structure

```plaintext
.
├── index.html       # Main HTML structure
├── style.css        # CSS for styling and responsiveness
├── script.js        # JavaScript code including Warshall's Algorithm and D3.js for visualization
└── README.md        # Project documentation

How It Works
Adding Nodes and Edges:

Users can add cities (nodes) and roads (edges) using the input fields.
Each new road creates a direct connection between two cities, displayed on the graph.
Warshall's Algorithm:

When the "Compute Reachability" button is clicked, Warshall's Algorithm is applied.
The algorithm checks all possible paths between cities to determine if there are indirect connections.
The reachable cities are highlighted on the graph.
Graph Visualization:

D3.js is used to draw nodes and edges.
The nodes change color based on reachability after running Warshall's Algorithm.
Code Snippet
Here's a short snippet showing the core of Warshall's Algorithm in this project:

function computeReachability() {
  let reach = adjacencyMatrix.map(row => row.slice());  // Copy adjacency matrix for reachability
  for (let k = 0; k < numNodes; k++) {
    for (let i = 0; i < numNodes; i++) {
      for (let j = 0; j < numNodes; j++) {
        reach[i][j] = reach[i][j] || (reach[i][k] && reach[k][j]);
      }
    }
  }
  visualizeGraph(reach, true);  // Update graph with reachable nodes
}

