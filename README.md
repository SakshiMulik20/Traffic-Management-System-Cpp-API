Traffic Management System - Backend Code (C++)
Overview
This C++ program simulates a basic Traffic Management System with the following functionalities:

View Traffic Data: Shows the status, vehicle count, and timestamp for predefined routes.
Simulate Traffic Lights: Simulates traffic light signals at different locations.
Find the Shortest Route: Uses Dijkstra’s Algorithm to compute the shortest path between locations.
Data Structures Used
1. Structures (struct)
The program defines a TrafficData structure to store traffic information such as:
cpp
Copy
Edit
struct TrafficData {
    string status;
    int vehicleCount;
    string timestamp;
};
This structure is used to store pre-defined traffic conditions for specific routes.
2. Arrays ([])
Traffic Data Storage

cpp
Copy
Edit
TrafficData trafficData[MAX] = { ... };
Stores traffic conditions for predefined routes.

Graph Representation (roadMatrix[MAX][MAX])

cpp
Copy
Edit
int roadMatrix[MAX][MAX] = { ... };
This Adjacency Matrix represents roads connecting different locations.
Each element in the matrix denotes the travel time between locations.
Location Names (locations[MAX])

cpp
Copy
Edit
string locations[MAX] = { ... };
Stores the names of different locations in the system.
Techniques Used
1. Graph Representation (Adjacency Matrix)
The system models roads between locations using a graph stored in an adjacency matrix:
cpp
Copy
Edit
int roadMatrix[MAX][MAX] = {
    {0, 8, 15, 12},
    {8, 0, 5, 0},
    {15, 5, 0, 6},
    {12, 0, 6, 0}
};
Vertices: Locations (Hadapsar, KP, Kothrud, VimanNagar).
Edges: Represent travel times between locations.
2. Shortest Path Calculation (Dijkstra’s Algorithm)
The function calculateOptimalRoute() finds the shortest travel time between two locations using Dijkstra’s Algorithm.
Steps in Dijkstra's Algorithm:
Initialize distances from the source as infinity (INT_MAX), except for the source itself (0).
Use a visited array (processed[]) to track processed nodes.
Pick the minimum distance vertex that is not yet processed.
Update the shortest paths to all its adjacent nodes.
Repeat until all vertices are processed.
3. User Interaction (Switch-Case via While Loop)
The program provides a menu-driven interface where the user can:
View traffic data (option 1)
Simulate traffic light signals (option 2)
Find the shortest route (option 3)
Exit the program (option 4)
4. Simulation of Traffic Lights
The function simulateTrafficLightScheduling(location) simulates traffic signals for a given location:
cpp
Copy
Edit
void simulateTrafficLightScheduling(string location) {
    cout << "Traffic Light at " << location << " is Green for 45 seconds." << endl;
    cout << "Traffic Light at " << location << " is Yellow for 5 seconds." << endl;
    cout << "Traffic Light at " << location << " is Red for 30 seconds." << endl;
}
This function models real-world traffic light behavior.
Code Flow
User selects an option from the menu.
Option 1 (View Traffic Data): Displays stored traffic information.
Option 2 (Simulate Traffic Light): Shows a predefined traffic light sequence.
Option 3 (Find Shortest Route):
User enters the start and end locations.
The program finds the shortest route using Dijkstra’s Algorithm.
Outputs the shortest travel time and path.
Option 4 (Exit): Terminates the program.
How to Run the Code
Compile the code using g++:
sh
Copy
Edit
g++ traffic_system.cpp -o traffic_system
Run the executable:
sh
Copy
Edit
./traffic_system
Possible Enhancements
Implement real-time traffic updates using sensor data.
Use priority queues (Min-Heap) in Dijkstra’s Algorithm to improve efficiency.
Add dynamic traffic light control based on real-time vehicle count.
