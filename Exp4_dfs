import sys

class ShortestPath:
  def __init__(self, start, end):
    self.start = start
    self.end = end
    self.shortLength = sys.maxsize

  def findPath(self):
    #start DFS from the start vertex
    self.dfs(self.start)
    #trace the route to output the path   
    self.trace_route()

  def dfs(self, vertex):
    global length
    
    #Increment the current path length by 1
    length +=1

    #1st base condition
    #return if current route is longer
    #than the already discovered route 
    if length > self.shortLength:
      return

    #2nd base condition
    #if reach the destination vertex
    #update the shortLength and
    #return to explore shorter routes 
    if vertex == self.end:
      self.shortLength = length
      return

    #mark vertex as visited to prevent overvisit
    visited[vertex] = 1
    
    #iterate through all unvisited neighbors vertices
    for i in range(N):
      if adjacencyM[vertex][i] == 1 and visited[i] == 0:
        nbr = i
      
        #update the preceding vertex of the neighbors
        prev[nbr] = vertex

        #recursively visit the neighbors
        #to continue search for the destination vertex
        self.dfs(nbr)

    #backtrack
    #visited[vertex] = 0
    length -=1

  #Function to trace the route using preceding nodes
  def trace_route(self):
    vertex = self.end
    route = []

    #start node has no preceding node
    #so loop until node->prev is null 
    while vertex != -1:
      route.append(vertices_names[vertex])
      vertex = prev[vertex]

    #reverse the route bring start to the front
    route.reverse()
    #output route
    print(route)
    
if __name__ == '__main__':
  #vertices or nodes
  vertices_names = ['A', 'B', 'C', 'D', 'E'];
  #number of vertices
  N = len(vertices_names)

  #Adjacency Matrix
  adjacencyM = [[0, 1, 0, 0, 0],
                [1, 0, 1, 0, 1],
                [0, 1, 0, 1, 1],
                [0, 0, 1 ,0, 1],
                [0, 1, 0, 1, 0]];

  #List mapping of vertices to mark them visited
  visited = [0 for x in range(N)]
  #List to stores preceding vertices
  prev = [-1 for x in range(N)]

  #Driver code
  sp = ShortestPath(0, 4)
  length = 0
  sp.findPath()