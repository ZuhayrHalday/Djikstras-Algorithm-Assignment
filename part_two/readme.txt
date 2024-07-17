SimulatorTwo README

Features Implemented:
1. Support for Taxi Nodes:
   - Added functionality to handle taxi nodes in the graph.
   - Taxi nodes can be specified in the input data, and optimal paths can be calculated from/to taxi nodes.

2. Support for Shop Companies:
   - Added functionality to associate shops with companies in the graph.
   - Shops can now have company affiliations, allowing for more detailed trip planning.
   - Shop companies can be specified in the input data, and optimal paths can be calculated with company restrictions.

3. Enhanced Trip Planning:
   - Extended the TripManager class to include methods for finding optimal paths based on taxi nodes and shop companies.
   - Users can now find optimal paths considering specific taxi nodes or shop companies, providing more flexibility in trip planning.

4. Improved Input Handling:
   - Modified the input format to support specifying taxi nodes and shop companies in addition to existing features.
   - Input data can now include information about taxi nodes and shop companies to facilitate more comprehensive trip planning.

5. Readability and Maintenance:
   - Ensured code readability and maintainability by organizing the implementation into separate classes and methods.
   - Comments and documentation have been added to clarify the purpose and functionality of each component.

Usage:
1. Input Format:
   - The input data should follow the specified format, including information about nodes, edges, taxi nodes, shop companies, and clients.
   - Refer to the provided examples or documentation for details on the input format.

2. Running the Program:
   - Compile the source code files (SimulatorTwo.java and its dependencies) using a Java compiler.
   - Execute the compiled program, providing the input data through standard input (console or file redirection).
   - The program will process the input, calculate optimal trips, and output the results to the console.

3. Output Format:
   - The program outputs formatted trip information for each client, including optimal paths from taxis to clients and from clients to shops.
   - Multiple solutions and costs are indicated where applicable, providing comprehensive trip planning details.
