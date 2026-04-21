# Minimum Spanning Tree Visualizer

A comprehensive interactive visualizer for Minimum Spanning Tree (MST) algorithms including **Kruskal's** and **Prim's** algorithms.

## 📋 Features

### Algorithms Implemented
- **Kruskal's Algorithm** - O(E log E)
  - Greedy approach using edge sorting
  - Union-Find data structure for cycle detection
  
- **Prim's Algorithm** - O(V²) or O(E log V)
  - Incremental MST growth from a starting vertex
  - Min-heap based priority selection

### Data Structures
- **Graph** - Adjacency list representation
- **Union-Find** - Disjoint Set Union with:
  - Path compression optimization
  - Union by rank optimization

### Visualization Features
- Interactive canvas-based graph visualization
- Step-by-step algorithm execution
- Color-coded MST edges
- Real-time weight calculation
- Auto-play functionality
- Previous/Next step navigation

## 📁 Project Structure

```
mst_visualizer/
├── backend/
│   ├── app.py                 # Flask application
│   ├── algorithms/
│   │   ├── mst.py            # Kruskal's and Prim's algorithms
│   │   └── __init__.py
│   └── datastructures/
│       ├── graph.py           # Graph data structure
│       ├── union_find.py      # Union-Find implementation
│       └── __init__.py
├── frontend/
│   ├── templates/
│   │   └── index.html         # Main HTML page
│   └── static/
│       ├── style.css          # Styling
│       └── script.js          # Interactive functionality
└── requirements.txt           # Python dependencies
```

## 🚀 Installation & Running

### Prerequisites
- Python 3.7+
- pip package manager

### Setup

1. Navigate to the project folder:
```bash
cd c:\Users\vivek\.p2\Downloads\mst_visualizer
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. Run the Flask application:
```bash
python backend/app.py
```

4. Open your browser and go to:
```
http://localhost:5000
```

## 📖 How to Use

### Basic Workflow
1. Click **"Load Example Graph"** to load a sample graph
2. Click either **"Run Kruskal's"** or **"Run Prim's"** algorithm button
3. Use the step controls to navigate through the algorithm execution:
   - Click **"Next ▶"** to go to the next step
   - Click **"◀ Previous"** to go to the previous step
   - Click **"Auto Play"** to automatically play through all steps

### Graph Information
- Click **"Graph Info"** to see details about the loaded graph
- View the current MST weight and number of edges
- See time complexity information for each algorithm

## 🎯 Algorithm Explanations

### Kruskal's Algorithm
1. Sort all edges by weight in ascending order
2. Use Union-Find to detect cycles
3. Iterate through sorted edges:
   - If adding edge doesn't create a cycle, add it to MST
   - Otherwise, skip the edge
4. Continue until MST has V-1 edges

**Time Complexity:** O(E log E) for sorting + O(E α(V)) for Union-Find = O(E log E)

### Prim's Algorithm
1. Start from an arbitrary vertex
2. Maintain a set of visited vertices
3. Use a min-heap to track minimum weight edges
4. Repeat until all vertices are visited:
   - Pick the minimum weight edge connecting visited to unvisited vertices
   - Add the new vertex to visited set
   - Add all its edges to the heap

**Time Complexity:** O(V²) with array or O(E log V) with min-heap

## 🔧 Customization

You can create custom graphs by modifying the example data or extending the frontend form submission functionality.

## 📚 Design & Analysis Notes

### Union-Find Optimizations
- **Path Compression:** When finding root, compress the path
- **Union by Rank:** Attach smaller tree to larger tree

Both optimizations reduce amortized time complexity to nearly O(1) per operation.

### Graph Representations
- **Adjacency List:** Used for sparse graphs (better space)
- **Edge List:** Used in Kruskal's for easy sorting

### MST Properties
- Any connected graph has at least one MST
- MST has exactly V-1 edges
- MST is not unique if edge weights are not distinct
- Total weight of MST is minimum among all spanning trees

## 🎓 Educational Value

This project demonstrates:
- Greedy algorithm design
- Graph algorithms and analysis
- Data structure applications (Union-Find)
- Algorithm visualization for learning
- Web-based interactive applications

## 📝 License

Free to use for educational purposes.

## 💡 Future Enhancements

- [ ] Support for directed graphs
- [ ] Additional algorithms (Borůvka's)
- [ ] Custom graph input form
- [ ] Export MST as image/data
- [ ] Performance benchmarking
- [ ] Larger graph handling
