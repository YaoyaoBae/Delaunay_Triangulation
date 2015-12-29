# Delaunay-Triangulation and Voronoi-Regions in images
This project consists of several parts which are joined together.

* **Triangulation**

    I always wanted to properly implement a delaunay triangulation. So here it is. It runs in
    Omega(n logn) and maybe also in O(n logn). The performance tends to tell that, some outputs
    as well but I can't really prove it.
    Anyway. You provide a list of points (tuples with x,y-coordinates!) and get back a list of
    triangles (also tuples with three points per triangle!).
    In the new version it also transforms the triangles into voronoi-regions 
    (polygons --> list of list of points).

* **Image-Triangulation**:

    This is the actual application of the delaunay-triangulation. You can specify a .jpg-Image
    and the program will perform some gauss-filtering and edge detection. Based on the contrast
    difference of the image there is a propability that a point is set on that spot (per pixel).
    With that there will be more points generated in areas with high contrast differences than
    in areas with equal colors and contrasts.
    These points will then be triangulated.
    After that each triangle will get colored with the approximate color of the pixels inside
    the triangle. Approximate because only the Vertices and the center of the triangle will be
    considered.
    These colored triangles will then be rendered into an new jpg-image.

* **Voronoi-Diagrams:**

    The delaunay-triangulation is taken and transformed in O(n) into voronoi-regions.
    These regions will then be rendered into an image just like the triangles before.
    The color is determined by the average color of each corner and the center of the
    polygon.

* **Point-Distribution:**

    There are different options for determining points in the image for triangulation.
    Points can be determined from edge-detection and are more common in parts of the image
    where bigger color-differences occure.
    Otherwise points can be distributed equally over the image space.
    The choice has a quite big influence on the outcome-image. For the delaunay-triangulation
    I prefer more points in edging areas. For voronoi-regions it looks more pleasant if the
    regions are more equally distributed.
    Anyway the results are stunning (in my opinion) :).

