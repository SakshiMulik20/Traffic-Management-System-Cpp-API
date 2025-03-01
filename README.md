## Traffic Management System - Backend Code (C++)
Overview
This C++ program simulates a basic Traffic Management System with the following functionalities:

1) View Traffic Data: Shows the status, vehicle count, and timestamp for predefined routes.
2) Simulate Traffic Lights: Simulates traffic light signals at different locations.
3) Find the Shortest Route: Uses Dijkstra’s Algorithm to compute the shortest path between locations.


## Data Structures Used
1. Structures (struct)
The program defines a TrafficData structure to store traffic information such as:

         struct TrafficData {
            string status;
            int vehicleCount;
            string timestamp;
            };
This structure is used to store pre-defined traffic conditions for specific routes.


3. Arrays ([])
--Traffic Data Storage

       TrafficData trafficData[MAX] = { ... };
-Stores traffic conditions for predefined routes.

--Graph Representation int (roadMatrix[MAX][MAX])
      
        int roadMatrix[MAX][MAX] = { ... };
-This Adjacency Matrix represents roads connecting different locations.
-Each element in the matrix denotes the travel time between locations.


--Location Names (locations[MAX])
      
        string locations[MAX] = { ... };
-Stores the names of different locations in the system.


## Techniques Used
1. Graph Representation (Adjacency Matrix)
The system models roads between locations using a graph stored in an adjacency matrix:

        int roadMatrix[MAX][MAX] = {
            {0, 8, 15, 12},
            {8, 0, 5, 0},
            {15, 5, 0, 6},
            {12, 0, 6, 0}
        };

    -Vertices: Locations (Hadapsar, KP, Kothrud, VimanNagar).
    -Edges: Represent travel times between locations.


2. Shortest Path Calculation (Dijkstra’s Algorithm)
The function calculateOptimalRoute() finds the shortest travel time between two locations using Dijkstra’s Algorithm.
     - Steps in Dijkstra's Algorithm:
       
        1)Initialize distances from the source as infinity (INT_MAX), except for the source itself (0).
       
       2)Use a visited array (processed[]) to track processed nodes.
       
       3)Pick the minimum distance vertex that is not yet processed.
       
       4)Update the shortest paths to all its adjacent nodes.
       
       5) Repeat until all vertices are processed.


3. User Interaction (Switch-Case via While Loop)
- The program provides a menu-driven interface where the user can:
    -View traffic data (option 1)
    -Simulate traffic light signals (option 2)
    -Find the shortest route (option 3)
    -Exit the program (option 4)


4. Simulation of Traffic Lights
The function simulateTrafficLightScheduling(location) simulates traffic signals for a given location:

        void simulateTrafficLightScheduling(string location) {
            cout << "Traffic Light at " << location << " is Green for 45 seconds." << endl;
            cout << "Traffic Light at " << location << " is Yellow for 5 seconds." << endl;
            cout << "Traffic Light at " << location << " is Red for 30 seconds." << endl;
        }
   - This function models real-world traffic light behavior.


                Code Flow
        User selects an option from the menu.


      Option 1 (View Traffic Data): Displays stored traffic information.

     Option 2 (Simulate Traffic Light): Shows a predefined traffic light sequence.

     Option 3 (Find Shortest Route):
        - User enters the start and end locations.
        -The program finds the shortest route using Dijkstra’s Algorithm.
        -Outputs the shortest travel time and path.
        
        Option 4 (Exit): Terminates the program.



