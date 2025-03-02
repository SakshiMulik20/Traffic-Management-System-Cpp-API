## 🚦 Traffic Management System - Backend (C++)

📌 Overview
This Traffic Management System is a C++ program that simulates traffic data monitoring, traffic light scheduling, and optimal route calculation using Dijkstra's Algorithm.

🔹 Key Features:

✅ View Traffic Data – Displays real-time traffic status, vehicle count, and timestamps.

✅ Simulate Traffic Lights – Models traffic signal sequences at different locations.

✅ Find Shortest Route – Computes the shortest path between locations using Dijkstra’s Algorithm.

🛠️ Data Structures Used

1️⃣ Structures (struct)

The program uses a TrafficData structure to store real-time traffic information:

          struct TrafficData {
    string status;
    int vehicleCount;
    string timestamp;
    };

This stores traffic conditions for predefined routes.

2️⃣ Arrays ([])

Used to store traffic data, graph representation, and location names:

Traffic Data Storage:

         TrafficData trafficData[MAX] = { ... };

Graph Representation (Adjacency Matrix):

         int roadMatrix[MAX][MAX] = { ... };

Location Names:

         string locations[MAX] = { ... };


## 🚀 Techniques Used

1️⃣ Graph Representation (Adjacency Matrix)

The system models roads between locations using a graph stored in an adjacency matrix:

         int roadMatrix[MAX][MAX] = {
    {0, 8, 15, 12},
    {8, 0, 5, 0},
    {15, 5, 0, 6},
    {12, 0, 6, 0}
    };
🔹 Vertices: Locations (Hadapsar, KP, Kothrud, VimanNagar).

🔹 Edges: Represent travel times between locations.

2️⃣ Shortest Path Calculation (Dijkstra’s Algorithm)

The function calculateOptimalRoute() finds the shortest travel time between locations using Dijkstra’s Algorithm:

✨ Steps in Dijkstra's Algorithm:

1️⃣ Initialize distances as infinity (INT_MAX), except for the source (0).

2️⃣ Use a visited array (processed[]) to track processed nodes.

3️⃣ Pick the minimum distance vertex that is not yet processed.

4️⃣ Update the shortest paths to all its adjacent nodes.

5️⃣ Repeat until all vertices are processed.

3️⃣ User Interaction (Menu-Driven Program)

The system provides a menu-driven interface where users can:

[1] View Traffic Data – Displays traffic status for predefined routes.

[2] Simulate Traffic Light – Models real-world traffic signals.

[3] Find Shortest Route – Uses Dijkstra’s Algorithm to compute optimal paths.

[4] Exit – Terminates the program.


4️⃣ Traffic Light Simulation

The function simulateTrafficLightScheduling(location) models real-world traffic light behavior:

         void simulateTrafficLightScheduling(string location) {
    cout << "Traffic Light at " << location << " is Green for 45 seconds." << endl;
    cout << "Traffic Light at " << location << " is Yellow for 5 seconds." << endl;
    cout << "Traffic Light at " << location << " is Red for 30 seconds." << endl;
         }

## 📌 Code Flow

📌 User selects an option from the menu:

✅ Option 1 - View Traffic Data: Displays stored traffic conditions.

✅ Option 2 - Simulate Traffic Light: Shows traffic light sequence.

✅ Option 3 - Find Shortest Route:

User enters start & end locations.

The system calculates shortest route using Dijkstra’s Algorithm.

Outputs travel time & path.

✅ Option 4 - Exit: Terminates the program.

📂 Installation & Usage

🔹 Prerequisites

Ensure you have:
✔️ C++ Compiler (G++) – Install via sudo apt install g++ (Linux) or MinGW (Windows).

🔹 Run the Program

1️⃣ Clone the Repository:


         git clone https://github.com/sakshimulik20/traffic-management-system.git
         cd traffic-management-system

2️⃣ Compile the Code:

         g++ traffic_management.cpp -o traffic_system

3️⃣ Run the Program:

         ./traffic_system

## 🎯 Future Enhancements
🔹 🚀 API Integration – Connect with a frontend using Flask/Node.js.

🔹 📊 Real-Time Traffic Data – Fetch live traffic data from APIs.

🔹 🌍 Google Maps Integration – Visualize routes dynamically.

🤝 Contributing

🚀 Feel free to contribute! Follow these steps:

1️⃣ Fork this repository.

2️⃣ Create a new branch: git checkout -b feature-branch

3️⃣ Commit changes: git commit -m "Added new feature"

4️⃣ Push the branch: git push origin feature-branch

5️⃣ Submit a Pull Request (PR) 🎉



📧 Contact

💬 Author: Sakshi Mulik

🔗 GitHub: sakshimulik20

📩 Email: sakshimulik20@gmail.com

🔹 Star 🌟 this repo if you find it useful! 🚀
