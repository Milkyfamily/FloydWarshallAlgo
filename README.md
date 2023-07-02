# FloydWarshallAlgo
Mid-term project for the course of University of Liverpool CSCK541 June-2023A

Rewrite Floyd’s algorithm to use recursion.

The Python code for an imperative version of Floyd’s algorithm is included below:

    import sys
    import itertools
    
    NO_PATH = sys.maxsize
    graph = [[0, 7, NO_PATH, 8],
    [NO_PATH, 0, 5, NO_PATH],
    [NO_PATH, NO_PATH, 0, 2],
    [NO_PATH, NO_PATH, NO_PATH, 0]]
    MAX_LENGTH = len(graph[0])

    def floyd(distance):
        """
        A simple implementation of Floyd's algorithm
        """
        for intermediate, start_node,end_node\
        in itertools.product\
        (range(MAX_LENGTH),range(MAX_LENGTH), range(MAX_LENGTH)):
      
            # Assume that if start_node and end_node are the same
            # then the distance would be zero
            if start_node == end_node:
                distance[start_node][end_node] = 0
                continue

            #return all possible paths and find the minimum
            distance[start_node][end_node] = min(distance[start_node][end_node],
                      distance[start_node][intermediate] + distance[intermediate][end_node] )
        #Any value that have sys.maxsize has no path
        print (distance)
    floyd(graph)

Write to PEP standards. Put under source control and write unit tests for each function. Write performance tests and check your version against the source code from above.

The output of the graph as below:

    [[0, 7, 12, 8],
     [9223372036854775807, 0, 5, 10],
     [9223372036854775807, 9223372036854775807, 0, 2],
     [9223372036854775807, 9223372036854775807, 9223372036854775807, 0]]
