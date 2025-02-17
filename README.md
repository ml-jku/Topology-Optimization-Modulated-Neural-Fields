# Generative Topology Optimization: Exploring Diverse Solutions in Structural Design

[//]: # (- [ArXiv ]&#40;&#41;)

- The code is combined with [Geometry-informed Neural Networks (GINNs)](https://github.com/ml-jku/GINNs-Geometry-informed-Neural-Networks).

---

Generative Topology Optimization (GenTO) is a novel method that uses neural networks to generate diverse and structurally compliant shapes without relying on pre-existing data.
Unlike traditional topology optimization methods, GenTO can explore multiple design solutions simultaneously, thanks to an explicit diversity constraint.
It optimizes material distribution iteratively with a solver-in-the-loop approach, producing varied shapes that meet design requirements efficiently.
Validated on both 2D and 3D problems, GenTO outperforms previous methods in diversity and speed, offering significant advancements in engineering and design flexibility.

<table style="width:1000px; border:none; border-collapse:collapse">
  <tr style="border:none">
    <td style="text-align:center; vertical-align:middle; width:50%; border:none;">
      <img src="media/cantilever-equidistant_9.png" alt="Diverse results on cantilever" width="400">
    </td>
    <td style="text-align:center; vertical-align:middle; width:50%; border:none;">
      <img src="media/DAB-cantilever.png" width="240">
    </td>
  </tr>
</table>




## Method overview

We parametrize shapes with a conditional neural field.
In each iteration, the network receives mesh locations and modulation vectors as input.
It outputs densities for each shape at these mesh points.
These densities are then used by a solver to calculate compliances and volumes, along with their gradients.
The diversity loss is determined by comparing the surface points of the shapes using the chamfer discrepancy.
This comparison helps compute the diversity loss and its gradient.


<img src="media/GenTO-method.png" alt="Description of the image" height="200">


## Results

The produced shapes are more diverse than the baseline, i.e., the Deflated Barrier method ([ArXiv](https://arxiv.org/abs/2004.11797)).

<table style="width:1000px; border:none; border-collapse:collapse">
  <tr style="border:none">
    <td style="text-align:center; vertical-align:middle; width:50%; border:none;">
      <img src="media/beam-equidistant_9.png" alt="Diverse results on cantilever" width="400">
    </td>
    <td style="text-align:center; vertical-align:middle; width:50%; border:none;">
      <img src="media/DAB-beam.png" width="240">
    </td>
  </tr>
</table>


The method also scales to 3D were it produces diverse modes for a jet engine bracket.
The following figure shows 3 modes from top and perspective view.


<img src="media/Jeb-combined_0_4_6.png" alt="Diverse results on cantilever" width="300">

[//]: # (## Citation)

[//]: # ()
[//]: # (```)

[//]: # ()
[//]: # (```)

