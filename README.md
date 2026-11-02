# RouteLab

An interactive graph visualizer comparing **Breadth-First Search**, **Depth-First Search**, and **Uniform Cost Search** on a weighted network of Pakistani cities.

Choose two cities, run a search, and watch the traversal reveal a route. Add your own cities and weighted connections to explore how the algorithms behave.

![Uniform Cost Search on the city network](docs/preview.png)

## What it demonstrates

- Animated traversal with distinct start, destination, visited, and route states.
- A route summary showing total distance, visited steps, and edge count.
- Custom nodes and positive weighted connections, held in memory for the current session.
- An SVG network that expands to include newly added nodes.
- Keyboard focus indicators, responsive layouts, and reduced-motion styling.

## Compare the algorithms

| Algorithm | Finds | Guarantee |
| --- | --- | --- |
| BFS | A route with the fewest edges | Minimum hops, not necessarily minimum distance |
| DFS | A route by exploring deeply first | No shortest-route guarantee |
| UCS | A route with the lowest total weight | Minimum distance with positive edge weights |

For the supplied Lahore–Karachi graph, BFS returns a route costing **2,210**, while UCS finds a route costing **1,160**. The graph is illustrative; distances are sample edge weights, not navigation guidance.

## Run locally

Requires Node.js 22 or newer and npm.

```sh
git clone https://github.com/Ibrahim-Iyaz/RouteLab.git
cd RouteLab
npm ci
npm run dev
```

Open the local address printed by Vite.

```sh
npm test          # Validate all algorithms against independent reference distances
npm run build     # Type-check and create the production bundle
npm run preview   # Serve the production bundle locally
```

The algorithm check covers all 81 ordered pairs in the supplied graph, verifies route edges and costs for all three algorithms, checks BFS minimum hops and UCS minimum weight, and checks disconnected-node behavior.

## Project structure

```text
src/Algorithms/   BFS, DFS, and UCS implementations
src/Components/  Graph, controls, node editor, and result summary
src/Data/        Initial city network and edge weights
scripts/         Algorithm verification
```

Built with React, TypeScript, Vite, and SVG. There is no backend or account setup. Custom graph edits reset when the page is reloaded.

## Author

[Ibrahim Iyaz](https://github.com/Ibrahim-Iyaz) · [LinkedIn](https://www.linkedin.com/in/ibrahim-iyaz)
