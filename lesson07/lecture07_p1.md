---
title: Lecture 7, Part 1 - Data and Viz basics, more on widgets
layout: lecture
visible_lec: true
visible_n: true
---

## Warm-Up Activity

1. What is the visualization trying to show?
1. What are its methods?
1. What are the strengths / weaknesses?

</br>
 * https://zzzev.com/movies

---

## This lecture

 * Data organization (quick)
 * Doing stuff with data
 * Dimensions of representation

</br>
</br>

## If time permits

 * Linked data
 * Grammar of Graphics
 * bqplot and dashboarding

---

# Data organization: A few notes

---

<!-- .slide: data-background-image="images/viz_diagram.svg.png" data-background-size="contain"-->

notes: Today we are going to discuss different sorts of data formats.

---

<!-- .slide: data-background-image="images/viz_diagram2.svg.png" data-background-size="contain"-->

notes: Usually we are going to be
able to make use of readers

---

<!-- .slide: class="two-floating-elements" -->

## Files, Data, and Organization

* Text
  * <span style="color:red">ASCII (raw)</span>
  * <span style="color:red">CSV / TSV</span>
  * JSON
* Binary
  * HDF5
  * PNG/BMP/GIF/JPG/etc
  * Excel
  * Arrow
* Query-based
  * SQL
  * JSON/REST

<div class="right" markdown=1>

<!--![](diagrams/row_col.svg)-->
<img src="diagrams/row_col.svg" alt="drawing" width="150"/>

<!--![](diagrams/hdf5pic.png)-->
<img src="images/hdf5pic.png" alt="drawing" width="250"/>

<img src="images/jsonex.png" alt="drawing" width="150"/>

</div>

notes:

we are predominatley using ASCII and CSV files in this class which is basically files with letters and numbers in rows and columns, but its worth mentioning that there *many* other ways data can be stored like in binary files to compress storage space or file formats that are ment for accessing a bunch like query-based file systems

read-write operations from disk are extremely time consuming, so raw text files come with massive overhead

REST = REpresentational State Transfer - web architecture that keeps clients and servers independent and queries using flexible JSON formatting.

---

## Doing Stuff with Data

Now that we understand a few ways that data can be stored, let's do some things
to it.

---

# Doing stuff with data

---

<div class="left">
![](images/palette.jpg)<!-- .element: style="height: 20em;" -->
</div>

<div class="right" style="font-size: 150%;">
<div style="height: 4.0em;"></div>
You have a palette of operations to apply.
</div>

---

## Filtering Operations

 * Relationships:
   * Equality, inequality
   * Quantitative value (less than, greater than)
   * Intersection, disjoint
 * Subsampling
   * Regular sampling
   * Randomized sampling
   * Nyquist frequency
 * Related data queries
   * Queries on other columns at fixed row location
   * External membership queries

notes: these are a lot of fancy words, but essentially we've already done this before - when we only plotted the eccentricity from the kepler data?  That was plotting a sort of equality

we also subsampled our data to make movies

---

## Relationships Examples

 * Equality
   * Identity
   * Quantitative values
 * Ordering or quantitative
   * Less than (or equal)
   * Greater than (or equal)
   * "Comes before" and "Comes after"
 * Set-based operations
   * "Is a member"
   * "Is not a member"
   * "Shares members"
   * "Shares no members"

---

## Examples

### Equality

```
value == "hello"
value == 10
```

### Ordering and Quantitative

```
value < 30
value > July 1, 2010
```

### Set-Based

```
value in ("red", "blue")
value not in (3.141, 2.7)
```

notes: again, these are a lot of fancy words, but we've already done this a lot before

we've done things based on equality and inequity in if-then statements

---

## Examples

### Equality

```
value == "hello"
value == 10
```

### Ordering and Quantitative

```
value < 30
value > July 1, 2010
```

### Set-Based

```
value in ("red", "blue")
value not in (3.141, 2.7)
```

We will often *mask* data to select just what we want to show.

notes: there are various ways to talk about it, but I usually use the term "masking" to talk about 

we'll do some quick examples

---

<br />
<br />
<br />

# Dimensions of representation

i.e. how can we represent data in visualizations?

---

## Representing Quantities

We can encode the values associated with a data point by modifying how we
express it.  To do so, we need to be able to identify the different components
of representation, and how we can scale between them.

---

## Dimensions of Representation

Given a single datum on a visualization, we can control several different
components of its representation.

 * Position

<!-- .slide: data-background-image="images/dimensions_1.svg" data-background-size="auto 50%" data-background-position="right 20% bottom 50%"-->

---

## Dimensions of Representation

Given a single datum on a visualization, we can control several different
components of its representation.

 * Position
 * Color

<!-- .slide: data-background-image="images/dimensions_2.svg" data-background-size="auto 50%" data-background-position="right 20% bottom 50%"-->

---

## Dimensions of Representation

Given a single datum on a visualization, we can control several different
components of its representation.

 * Position
 * Color
 * Size

<!-- .slide: data-background-image="images/dimensions_3.svg" data-background-size="auto 50%" data-background-position="right 20% bottom 50%"-->

---

## Dimensions of Representation

Given a single datum on a visualization, we can control several different
components of its representation.

 * Position
 * Color
 * Size
 * Shape

<!-- .slide: data-background-image="images/dimensions_4.svg" data-background-size="auto 50%" data-background-position="right 20% bottom 50%"-->

---

## Dimensions of Representation

Given a single datum on a visualization, we can control several different
components of its representation.

 * Position
 * Color
 * Size
 * Shape
 * Relationship

<!-- .slide: data-background-image="images/dimensions_5.svg" data-background-size="auto 50%" data-background-position="right 20% bottom 50%"-->

---

## Dimensions of Representation

Given a single datum on a visualization, we can control several different
components of its representation.

 * Position
 * Color
 * Size
 * Shape
 * Relationship
 * Motion

<!-- .slide: data-background-image="images/dimensions_6.gif" data-background-size="auto 50%" data-background-position="right 20% bottom 50%"-->

---


<video width="1024" height="576" controls="controls">  
    <source src="./images/jeff.mp4"  />   
    <!-- <track src="subtitles_en.vtt" kind="subtitles" srclang="en" label="English"> -->     
    Nav doesn't support html5 video
</video>

Link - https://www.youtube.com/watch?v=kY-pUxKQMUE

---

[This plot](http://iopscience.iop.org/article/10.1088/0004-637X/763/1/38/meta#apj455166f4)
might be a bit too busy.

<img src="images/toomuch.png" height="600">

Article Link - https://iopscience.iop.org/article/10.1088/0004-637X/763/1/38

---

Someone on [Reddit](https://www.reddit.com/r/dataisugly/comments/8msftx/the_marvel_that_is_3d_stacked_scatter_pie_columns) designed a 3D Stacked Scatter Pie Column plot ... as an example of what not to do.

<img src="images/scatterpie.png" height="600">

---

## Take away: think carefully about what you choose to add to your viz!

---

# Let's add another layer of complexity to our plots by adding in some interactivity in Python!
