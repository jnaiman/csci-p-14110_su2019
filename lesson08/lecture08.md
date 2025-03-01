---
title: Lecture 8 - Into the 3rd Dimension!
layout: lecture
visible_lec: true
visible_n: true
---

## Warm-Up Activity

1. What is the visualization trying to show?
1. What are its methods?
1. What are the strengths / weaknesses?

</br>
 * https://thetruesize.com/

---

## This lecture

 * Scientific Visualization with 3-dimensional data
 * Data representation in 3-dimensions
 

---

## Information Visualization

So far: Spatial encoding is chosen by the designer

<img src="images/circlesTree.png" width="500"/>

notes: so far, a lot of our placement of objects has been up to us in many ways

this was true of the dashboard - we can order our plots in many differnt ways!

---

## Scientific Visualization

Sci Viz: Spatial encoding is provided in the data

<img src="images/orf2D.png" width="500"/>

notes: but with sci viz, we are usually dealing with spatial data - so we are told by the 
science where we should be placing things in 3D space

we did this sort of thing in 2D for data on maps, but this gives even more detail on 
where each data point should be placed

---

## Rendering Images with Data
 
<iframe width="800" height="450" src="https://www.youtube.com/embed/NEzJH-JrAdw?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe> 
notes: so, ultimately, what we want to do is take our 3D objects and make them into images to show off

---

## Spatial Data

 1. Geometry
  * Volumetric Fields

<img src="images/smoke.gif" width="800"/>

note: there are different kinds of spatial datasets that might make up our 3d space and thus that we have to consider when we are rendering an image

Here is shown some volumetric data - i.e. you are given points of things in 3D space

shown here is a simulation in Houdini (a special effects software package) showing smoke rising

The left plot shows the simulation data points, the middle plot shows how they are interpolated to a surface and the right shows how they are "rendered" i.e. made into a movie using a smoke "shader" which dictates how light rays will travel through the object

---

## Spatial Data

 1. Geometry
   * Polygons

<img src="images/wheel.gif" width="800"/>

notes: another thing you will see a lot is 3-dimensional surfaces like the one shown here

Instead of specifying data at each point in the 3D volume, we are specifying the surface - i.e. an interconnected list of polygons that makes this shape



---

## Spatial Data

 1. Geometry
   * Polygons
   * Point Clouds

<img src="images/cme.gif" width="800"/>

notes:

Sometimes you'll see data shown by points.  Before, we were showing data that "filled up" the space, but here point clouds are almost like infinitely small data points at specific locations in space

point clouds can be static, or they can have physics which make them a "particle system".

FYI this is a non-final render of some data from the "Solar Super Storms" movie that the AVL created

---

## Spatial Data

 2. Volumetric Fields

<img src="images/redDropShort.gif" width="600"/>

notes:
How do you represent something like this with data?

You need scalars to describe things like material.

You need vectors to describe things like motion (velocity). 

---

## Spatial Data

 2. Volumetric Fields
    * Scalar

<img src="images/grids.gif" width="600"/>

notes:
This sequence reveals the underlying 3D grids of several scalar fields including:

H1 density

H2 density

photogamma

temperature

metallicity

Basically, you can think of the centers of each cubes specifying where the data points actually are - more densely packed cubes means *higher resolution* data

---

## Spatial Data

 2. Volumetric Fields
    * Scalar

<img src="images/sapasmons.jpg" width="500"/>

notes:
Fields can be 2D or 3D. Images can be used as 2D data fields.

AVL used this image from the Magellan satellite to create a "displacement map" for this venusian volcano called "Sapas Mons".

2D fields can also be layered in formats common to GIS, or Hollywood formats like EXR.

---

## Spatial Data

 2. Volumetric Fields
    * Scalar
    * Vector

[Windy Weather Map](https://www.windy.com)

<img src="images/maria.png" width="600"/>

notes:
Windy is an interactive wind velocity map. It's always interesting to look at, but especially during hurricane season. I captured this image as Hurricane Maria flirted with the East coast in Sept 2017.

---

## Spatial Data

 2. Volumetric Fields
    * Scalar
    * Vector

Its even possible to do this in real time: [Earth map](https://earth.nullschool.net/)



---

## Spatial Data

 2. Volumetric Fields
    * Scalar
    * Vector

<img src="images/streamlines.gif" width="600"/>

notes:
In this visualization we're seeing 3D velocity streamlines.

We're ALSO seeing a scalar volume called "vorticity" which is directly derived from the velocity field by taking a mathematical operation called the "curl".

In this case we are plotting *both* scalar (volume glow) and vector (streaming lines) data in the same viz!

Also from solar super storms

---

## Spatial Data

 2. Volumetric Fields
    * Uniform or non-uniform
    * Rectangular or non-rectangular

<img src="images/gridTypes.gif" width="400"/>

notes:
Adaptive mesh refinement is an especially efficient 3D storage for datatypes that have small areas of high detail.

This is why dealing with scientific data can be a little tricky - it can be hard to make surfaces or volumes out of irregularly gridded data

---

## Spatial Data Types

 1. Statistical
    * Star species
    * Atom prevalence
 1. Observational
    * Telescope images
    * Microscope images
    * LIDAR
 1. Simulated by computer models
    * First principles physics
    * Astronomy, geology, biology

---

## Visualizing Point Data

 * Dots with scale

<img src="images/pointCloud.gif" width="600"/>

notes: some other, less used data types include things like dots with scale

---

## Visualizing Point Data

 * Dots with scale
 * Sprites

<img src="images/energy.gif" width="600"/>

notes:
All the moving dots in this video are represented by a gaussian splat image. You can see how they are adjusted to be different size and color (the important things are the purple ones)

FYI this is a little pre-final version of an upcoming movie called "Birth of Planet Earth"

---

## Visualizing Point Data

 * Dots with scale
 * Sprites

<img src="images/energyLetters.gif" width="600"/>

notes:
But gaussian blur isn't the only way to put a sprite on a point. This version used text instead. (purple q's instead of sprites)

---

## Visualizing Point Data

 * Dots with scale
 * Sprites
 * Meshing

<img src="images/canup.gif" width="600"/>

notes:
This is a test AVL worked on with an SPH "smooth particle hydrodynamics" dataset where we created a surface across points. The surface was generated at a density threshold - aka, it was an infinitely thin shell shrinkwrapped onto all particles that were above a certain density.

This is a way to turn particles into surfaces or polygons.

SPH, aka smooth particle hydrodynamics is the natural extension of the gravitational rendering that we are doing in this course - only you also take into account how gas particles interact hydrodynamically as well as gravitationally

---

## Visualizing Polygons

 * Vector lines with width, can be filled

<img src="images/platecarree.png" width="600"/>

notes:
We can also use polygons to make things like maps instead of 3D geometry.

---

## Visualizing Polygons

 * Vector lines with width, can be filled
 * Direct rendering of architectural schematics

<img src="images/lsst.gif" width="600"/>

notes:
Sometimes you will be given a description of geometric objects that you need to construct.

---

## Visualizing Polygons

 * Vector lines with width, can be filled
 * Direct rendering of architectural schematics
 * Direct rendering of 3D scans (pre-meshed)

<img src="images/mammoth.gif" width="600"/>

notes:
Sometimes you will get something that was originally generated from a point cloud but has already been meshed. Domain experts sometimes have access to better meshing tools, particularly in the realm of 3D scanning.

---

## Visualizing Scalar Fields

 * Slice

<img src="images/mri.png" width="600"/>

notes:
Even if you're not showing your final visualization as a slice, this is a good step for understanding and troubleshooting. As we've mentioned before, reducing dimensionality makes things clearer to the human brain.  

Therefore, "slicing" for volumetric data is a nice way to get a handle on your dataset.

---

## Visualizing Scalar Fields

 * Slice
 * Isosurface

<img src="images/isocontours.png" width="400"/>

notes:
You have probably seen this type of topographic map where lines indicate elevation. These lines are called isocontours. You can combine isocontours to get isosurfaces.

---

## Visualizing Scalar Fields

 * Slice
 * Isosurface

<img src="images/isosurfaces.png" width="700"/>

notes:
This is an isosurface of a tornado-forming storm cloud, and another of a supernova that the scientist called "the walnut".

Isosurfaces can make analysis easier.

---

## Visualizing Scalar Fields

 * Slice
 * Isosurface
 * 3D Volumetric Rendering

<img src="images/bock.gif" width="600"/>

notes:
But of course, you can always render the volume as a volume too. This is a volumetric tornado-forming storm cloud by Dave Bock who also works at the NCSA. 

While this looks similar to the volume rendering at the beginning of class its a better representation of reality - this includes a lot more physics, making it a scientific dataset.

---

## Visualizing Vector Fields

 * Arrow glyphs

<img src="images/arrows.gif" width="700"/>

notes:
vectors are often represented with arrows at specific points

I think this is magnetic field lines during a solar flare?

---

## Visualizing Vector Fields

 * Arrow glyphs
 * Streamlines / Streamtubes
    * Particle Advection!

<img src="images/tornado.gif" width="600"/>

notes:
But you can also show streamlines, which track vectors across the whole grid. Particle advection is releasing massless particles into a vector field, letting the vectors push them around, and tracing their progress.

This tornado visualization actually shows arrow on the ground AND streamlines in the air.

Arrows showing motion are something you might want to consider for your visualizations.

---

## yt

yt is an open-source, permissively-licensed python package for analyzing and visualizing volumetric data.

[yt-project.org](https://yt-project.org/)

There is a big yt community at Harvard as well as the iSchool at University of Illinois and NCSA!

---

## A note about RGB color wheels

<img src="http://dawnsbrain.com/wp-content/uploads/2009/03/rgb-color-wheel-lg.jpg" width="600"/>

notes: you'll often see colors expressed by triplet (some times 4) colors

these are RGB sequences or combinations of Red-Green-Blue colors

basically RGB combinations make up all the colors you see on this colorwheel and is a useful shorthand to encode colors

sometimes instead of 0-255 for levels you'll see this encoded as 0-1 but it means the same thing for our purposes





