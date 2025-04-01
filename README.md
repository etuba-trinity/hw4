# Q1 - Range class (20 pts)
Problem motivation: Numerical ranges are used for a wide variety of tasks, including cartography, genomics, and computer graphics. A range is defined as all numbers between a minimum and maximum value. For our purposes we will only consider inclusive ranges, meaning that the minimum and maximum values are considered to be within the range. Several operations are commonly performed on numerical ranges, including determining if a value is within the range, finding the overlap of a range, etc.
Problem description: For this question, you will write a Java class named Range to maintain information about an inclusive numerical range with a minimum and maximum value. Your class will contain private fields to store the minimum and maximum values of a range, and your class must contain the public constructors and methods described below.
Constructors:
A constructor that takes no arguments and returns a Range from 0.0 to 0.0
A constructor that takes 2 arguments, which should be the minimum and maximum values of the Range (in that order - minimum first, maximum second). If the provided minimum value is greater than the maximum value, then a Range from 0.0 to 0.0 should be returned.
## Methods:
.toString() - this method should return the Range as a String formatted as 
"[MIN to MAX]"
where MIN and MAX are replaced with the appropriate numbers. For example, for a Range spanning from 4.2 through 9.5, the .toString method should return the String "[4.2 to 9.5]".
.getMin() - should return the minimum value within the Range
.getMax() - should return the maximum value within the Range
.length() - should return the size of the Range
.contains(double) - should return true if the argument lies within the inclusive Range, false otherwise
.contains(Range) - should return true if the argument Range lies entirely within the calling Range, false otherwise. For example, the Range [4-5] is contained entirely within the Range [3-6], so if [3-6] is the calling Range and [4-5] is the argument Range, this method should return true. However, since the Range [4-7] is not entirely contained within the Range [3-6], if [3-6] is the calling Range and [4-7] is the argument Range, this method should return false.
.overlaps(Range) - should return true if the calling and argument Ranges overlap at any point (including their inclusive end points), and false otherwise. For example, the Ranges [3-6] and [4-7] overlap, so the method should return true; while the Ranges [3-6] and [7-9] do not overlap, so the method should return false.
.intersection(Range) - should return a Range of the intersection of the calling and argument Ranges. For example, the Ranges [3-6] and [4-7] intersect in the Range [4-6]. If the two Ranges do not overlap, this method should return a Range from 0.0 to 0.0.


See the following UML diagram and the tester code for the complete list of methods required:
### Range class
## Fields
double min
double max
## Methods
toString() -> String
getMin() -> double
getMax() -> double
length() -> double
contains(double) -> boolean
contains(Range) -> boolean
overlaps(Range) -> boolean
intersection(Range) -> Range


Hints & Tips:
Remember that you can call other methods within your class, which may be useful. For example, when you write the intersection method, the overlaps method may be helpful.
All Ranges for this assignment are considered to be inclusive. So a Range from 0 to 4 and a Range from 4 to 8 do overlap with each other with an intersection Range from 4 to 4.

# Q2 - Rectangle class (20 pts)
Problem motivation: Performing geometric operations on shapes is fundamental to computer graphics, game development, engineering, and many other practical applications. In future homework assignments you will be creating a sprite-based video game that will require you to find the intersections of rectangles of various sizes and in various positions. While you may or may not directly use this class for that future assignment, it will be valuable to reason about the geometric logic of rectangles in preparation for that work.
## Problem description: 
You will write a class named Rectangle that describes the location and size of a rectangle in a 2D cartesian coordinate system. All of our rectangles will be "axis-aligned," meaning that their sides are parallel to the x-axis and y-axis (not rotated). All fields of this class are entirely up to you, but your class must include the following constructors and methods.
## Constructors:
A constructor that takes no arguments and creates an "empty" Rectangle whose center point is at the origin of the coordinate plane (0,0) and has a width and height of 0 units.
A constructor that takes 2 double arguments, x and y, which should create a "unit" Rectangle whose center point is at the coordinate (x,y) with a width and height of 1 unit.
A constructor that takes 4 double arguments, x, y, width and height, which should create a Rectangle whose center point is at the coordinate (x,y) and has the specified width and height.
## Methods:
.toString() - this method should return the Rectangle as a String formatted as:
 "(XCENTER,YCENTER) WIDTH by HEIGHT"
where XCENTER and YCENTER describe the center point of the Rectangle and WIDTH and HEIGHT are what they sound like. For example, a unit Rectangle created by the no-argument constructor described above should return the String "(0.0,0.0) 0.0 by 0.0". Please use exactly this formatting and spacing.
.getCenterX() - should return the x-coordinate of the midpoint of the rectangle
.getCenterY() - should return the y-coordinate of the midpoint of the rectangle
.getWidth() - should return the width of the rectangle
.getHeight() - should return the height of the rectangle
.area() - should return the area of the rectangle
.perimeter() - should return the perimeter of the rectangle
.isSquare() - should return true if the rectangle is a square (has equal sides) and false otherwise
.contains(X ,Y) - should return true if the specified (x,y) coordinate lies within the rectangle (or along an edge of the rectangle) and false otherwise
.overlaps(Rectangle) - should return true if the calling rectangle and the argument rectangle intersects or overlaps with each other (even at a single point), and false otherwise
.intersection(Rectangle) - should return a new Rectangle instance that is the intersection of the calling and argument rectangles. If the rectangles do not intersect/overlap, then return the "empty" Rectangle with a center point of (0,0) and width and height of 0.

See the following UML diagram and the tester code for the complete list of methods required:

### Rectangle class
## Fields
//Determine your own fields
## Constructors
Rectangle()
Rectangle(double, double)
Rectangle(double, double, double, double)
Methods
toString() -> String
getCenterX() -> double
getCenterY() -> double
getWidth() -> double
getHeight() -> double
area() -> double
perimeter() -> double
isSquare() -> boolean
contains(double,double) -> boolean
overlaps(Rectangle) -> boolean
intersection(Rectangle) -> Rectangle


Hints & Tips:
Remember that you can call other methods within your class, which may be useful. It may also be useful to utilize the Range class written for Q1 for portions of Q2 - it's not required, but you may find yourself logically asking questions like "do these x-coordinate ranges overlap?" and the Range class may already do that for you.
