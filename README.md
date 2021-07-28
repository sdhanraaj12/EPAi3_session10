# EPAi3 Session 10 Assignment
## Sequence Types
#### Objective 1[pts:400]: 
#### Create a Polygon Class:
   1. where initializer takes in:
       1. number of edges/vertices
       2. circumradius
   2. that can provide these properties:
       1. number of edges
       2. number of vertices
       3. interior angle
       4. edge length
       5. apothem
       6. area
       7. perimeter
   3. that has these functionalities:
       1. a proper _ _ _repr_ _ _ function
       2. implements equality (==) based on # vertices and circumradius (_ _ _eq_ _ _)
       3. implements > based on number of vertices only (_ _ _gt_ _ _) 

#### Approach for objective 1: 

#### __regular_polygon__ :
+ This class is used to define regular polygons of 'n' sides and 'r' circum_radius. They have the below attributes and methods defined. Additionally dunder functions __eq__, __gt__ and __repr__ have been overwritten
    
    ##### Attributes
    * num_of_sides : int
        - Number of edges/vertices of a regular polygon
    * circum_radius : float
        - The circum radius of the regular polygo
    * interior_angle : float
        - Interior angle of the regular polygon
    * edge_length : float
        - Length of the sides of the regular polygon
    * apothem : float
        - The length of the perpendicular line drawn from the center of the polygon to one of its sides
    * area : float
        - The total area of the regular polygon
    * perimeter : float
        - The perimeter of the regular polygon
    
    ##### Methods
    * __init__ (self, num_of_sides, circum_radius)
        - Used to initialize the regular_polygon objects, with the num_of_sides and circum_radius parameters passed.
        - input: num_of_sides: int and circum_radius: float
        - return: None
    * __set_polygon_property__ ()
        - This method computes the interior_angle, edge_length, apothem, area and perimeter
        - Set each of the above as object property
        - input: None (access object attribute num_of_sides: int and circum_radius: float)
        - return: None
    * __repr__ (self)
        - Overwrites the default class object representation to 'This is a regular polygon with {self.num_of_sides} sides and {self.circum_radius} unit circum_radius'
        - input - None
        - return - String - Class object representation
    * __eq__ (self, other: object)
        - Checks the equality of the objects passed based on the number of vertices and circum radius
        - input - other, object to be compared
        - return - bool, True if the two objects are same, else False
    * __gt__ (self, other: object)
        - Checks if one object is '>' than the other based on the number of vertices
        - This method computes larger polygons based on the num_of_sides
        - input - other, object to be compared
        - return - bool, True if the self is larger, else False

### Objective 2[pts:600]: 
#### Implement a Custom Polygon sequence type:
   1. where initializer takes in:
       1. number of vertices for largest polygon in the sequence
       2. common circumradius for all polygons
   2. that can provide these properties:
       1. max efficiency polygon: returns the Polygon with the highest area: perimeter ratio
   3. that has these functionalities:
       1. functions as a sequence type (_ _ _getitem_ _ _)
       2. supports the len() functio
       3. has a proper representation (_ _ _repr_ _ _)

#### custom_polygon_sequence :
+ This class creates a sequence of polygon objects. It has the following attributes and methods

    ##### Attributes
    * largest_num_of_sides : int
        - The polygon with largest number of sides in the sequence
    * circum_rad : float
        - The common circum radius of all the polygons in the sequence
    * area_peri_ratios : dict()
        - The dictionary to store the area and perimeter as values and vertices as keys

    ##### Methods
    * __init__ (largest_num_of_sides, circum_rad)
        - This is a contructor for the custom_polygon_sequence class
        - The method takes largest_num_of_sides, circum_rad stores them as attribute to the class object
        - input - largest_num_of_sides: int, circum_rad: float
        - return - None
    * __getitem__ (vertex)
        - This method implements getitem[index] for the sequence object, based on the vertex argument passed, the corresponding polygon object's  
        - input - vertex: integer index
        - return - custom_polygon_sequence._poly_ratio(vertex)
    * __len__ ()
        - This method implements in the len() function on the sequence object
        - input - sequence object
        - return - length of the sequence object integer
    * __repr__ ()
        - This method overrides the default class object representation to 'This is a polygon sequence with the largest polygon having {self.largest_num_of_sides} sides and each polygon having {self.circum_rad} unit circum_radius'
    * __max_efficiency_polygon__ ()
        - This method computes the polygon with maximum area-perimeter ratio
        - input - None
        - return - The area-permiter ratio of the max efficient polygon is {self.area_peri_ratios[key]} with {key} vertices
    * ___poly_ratio__ (int, circum_rad)
        - This is a static method which computes the ratio between area and perimeter of each of the polygon
        - input - vertex - number of sides of the polygon and circum_rad - the circumference radius of the regular polygon
        - return - area/perimeter - float
