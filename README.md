# position-analysis
This repository contains my implementation of the shape graph and instantaneous inference of outfield positions according to the algorithms proposed by Brandes et al. 

The shape graph is a novel proximity graph based on the Delaunay triangulation. It aims to stabilize it by removing unstable edges (i.e., edges that disappear and reappear for small perturbations of the graph). When used on soccer tracking data, one can find the current team shape by applying the shape graph at any time frame. Additionally, one can infer the instantaneous positions of a team by applying the shape graph to the outfield players of one team and splitting twice along the barycenters of its internal faces. The positions of the players consist of 2D-tuples, with their horizontal and vertical coordinates taking integer values between -2 (left/bottom) and 2 (right/top). For example, a player with position coordinates (-2, -2) represents the left back, while a player with coordinates (1, 2) will be the right central striker.

This implementation is based on Python. The function frame_to_shape_graph takes as input a dictionary of players as keys and 2D-coordinate tuples as values (in metres) and returns the shape graph as a networkX.graph made up of nodes and edges. The function frame_to_positions takes the same input as frame_to_shape_graph, and returns a dictionary of players as keys and 2D position matrix coordinate tuples. The implementation can be used to conduct soccer analysis using positional data, like tracking data or event data containing player positions.

Find the paper following this link: https://rdcu.be/fapYR

For any questions about the implementation, feel free to contact me via mail: ruven21ugas@gmail.com
