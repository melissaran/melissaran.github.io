---
layout: post
title: sanctuary at sea
description: more procedural buildings!
img: /img/sasicon.png
---

Project of spring, 2018. Second human habitat project.

<a href="https://melissaran.itch.io/sanctuary-at-sea">
<span class="biglink">
    download on itch.io
</span>
</a>

<div class="img_row">
	<img class="col three" src="{{ site.baseurl }}/img/sas14.png" alt="" title="screenshot"/>
</div>

<iframe width="100%" height="315" src="https://www.youtube.com/embed/Xjvgdq2FDt8" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<div class="img_row">
	<img class="col three" src="{{ site.baseurl }}/img/sas13.png" alt="" title="example image"/>
</div>
<div class="col three caption">
	Screenshots of the final product.
</div>
Sanctuary At Sea is a procedural art generator. Players generate an infinite variety of homes with the press of a key, on a small island or right on a vast sea!
Each home is algorithm generated and unique, from it’s volume, to the arrangement of its windows.
Sanctuary at Sea was made as a piece of art, from the algorithms to the final visualization.

Below are intermediate stages of this project, and then a simple explanation of my process. I made many compromises, hard decisions and bad decisions while making this project, though in the end, I'm very happy with it's reception.

<div class="img_row">
	<img class="col one" src="{{ site.baseurl }}/img/sas1.png" alt="" title="stage1"/>
	<img class="col two" src="{{ site.baseurl }}/img/sas2.png" alt="" title="stage1"/>
</div>
<div class="col three caption">
	Stage one. Buildings have funky volumes.
</div>

<div class="img_row">
	<img class="col two" src="{{ site.baseurl }}/img/sas5.png" alt="" title="stage2"/>
	<img class="col one" src="{{ site.baseurl }}/img/sas4.png" alt="" title="stage2"/>
</div>
<div class="img_row">
	<img class="col three" src="{{ site.baseurl }}/img/sas7.png" alt="" title="stage2"/>
</div>
<div class="col three caption">
	Stage two. Ponyo-looking.
</div>

<div class="img_row">
	<img class="col one" src="{{ site.baseurl }}/img/sas9.png" alt="" title="stage1"/>
	<img class="col one" src="{{ site.baseurl }}/img/sas10.png" alt="" title="stage1"/>
	<img class="col one" src="{{ site.baseurl }}/img/sas11.png" alt="" title="stage1"/>
</div>
<div class="col three caption">
	Stage three. Different look.
</div>

<div class="img_row">
	<img class="col three" src="{{ site.baseurl }}/img/sas16.png" alt="" title="stage2"/>
</div>
<div class="img_row">
	<img class="col three" src="{{ site.baseurl }}/img/sas15.png" alt="" title="stage2"/>
</div>
<br/>

Here is a rough outline of the algorithm:
1) The volume of the house is randomly determined, and represented with a 3d array.
2) The walls of the house are “unwrapped” from the volume, and flattened into 2d arrays. Modules like windows, with varying heights and widths can then be randomly inserted into the wall.
3) Roofs are generated from the volume with one of two algorithms: one for an A roof, one for a hipped roof. Roofs are represented by 3d arrays.
4) All arrays are finally translated from data to a beautiful building, during the final stage of construction! Some mesh operations are necessary, like combining and generating new UVs, so that the textures of modules (the walls, roof pieces, etc) look non-repetitive.

<div class="img_row">
	<img class="col three" src="{{ site.baseurl }}/img/skybox.gif" alt="" title="stage2"/>
</div>
<br/>

Sanctuary At Sea also features a dynamically lit skybox, with billowing clouds and changing colors. It’s not a particle system or a video, but one shader!
Here’s the rough idea behind the skybox shader:
The sun is represented by a vector. All effects are some operation using the sun vector, and the “normal” of the clouds. For example, the halo effect is a combination of the cloud alpha, and the dot product of the cloud normal and the sun vector. (for extra bump, the clouds are normal mapped!)

<iframe width="100%" height="384" src="https://www.youtube.com/embed/qBtjZltZlKo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
