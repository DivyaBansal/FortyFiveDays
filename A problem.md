  
You are an expert in the game "Alphabetical Countries" or "Countries of the World." In this game, players take turns naming a country, with the next player having to name a country that begins with the last letter of the previous country's name. The game can continue until one player is unable to come up with a country name. In which order of countries should the game be played such that it lasts the longest? In other words, what would be the longest sequence of countries to play this game?

Greedy:
Play out all possible sequences, return the longest one

Efficient?
Pretty sure can be solved by graph traversal
But DFS in cyclic graph is a bit challenging

Data Structure ideas:
- Graph with countries as nodes and connections as edges
- Graph with alphabets as nodes and number of paths between the alphabets as weighted edges