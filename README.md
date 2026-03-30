# position-analysis
This repository contains my implementation of the shape graph and inference of instantaneous positions according to the approach of

[Brandes, Sotudeh, Parlak, Laffranchi & Erkul (2025). Shape graphs and the instantaneous inference of tactical positions in soccer. npj Complexity 2(1):25](https://dx.doi.org/10.1038/s44260-025-00047-x)

The shape graph is a novel proximity graph based on Delaunay triangulation. It discards edges close to being ambiguous (i.e., edges that are chords in a face of near co-circular points). When used on soccer tracking data, the current team shape is represented by the shape graph of any given time frame. Additionally, one can infer instantaneous tactical positions of a team by applying the shape graph to the outfield players of a team.

This implementation uses Python. The function `frame_to_shape_graph` takes as input a dictionary of players as keys and 2D-coordinate tuples as values (in metres) and returns the shape graph as a networkX.graph made up of nodes and edges. The function `frame_to_positions` takes the same input as `frame_to_shape_graph`, and returns a dictionary of players as keys and 2D position matrix coordinate tuples. Horizontal and vertical coordinates take integer values between -2 (left/bottom) and 2 (right/top) to represent ordinal levels. For example, a player with position coordinates (-2,-2) is interpreted to be a left back, while a player with coordinates (1,2) will be a right center forward.

The implementation can thus be used to conduct soccer analysis using positional data, like tracking data or event data containing player positions.

A demo notebook with example use cases will follow soon. For any questions about the implementation, feel free to contact me via mail: ruven21ugas@gmail.com
