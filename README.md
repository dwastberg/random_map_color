Random Map Color
=====

A simple function for generating a palet of visually distinct random colors to use with, for example, qualitative Choropleth maps. The aproach for measuring how visually distinct the colors are is losely inspired by the follwing article: https://www.hindawi.com/journals/mpe/2018/4652526

The function works by sampling a large number of colors in a restricted HSV space and then iteratively selecting the color that maximizes the minimum distance to the already selected colors.

Usage:
```python
gen_random_colors(n, h_range=(0.0, 1.0), s_range=(0.2, 1.0), v_range=(0.6, 1.0))
``` 
returns n rgb triplets of visually distinct colors.  By changing the `h_range`,  `s_range` and `v_range` variables you can limit the HSV color space that will be sampled. For example using `s_range=(0.2,0.5)` and `v_range = (0.8,1)` will limit your output to lower saturation, higher value color, giving a more pastel color palet.  Setting the minimum value of `s_range` or `v_range` to below 0.2 can lead inconsistent results. For the best results the `v_range` should be at least 0.5.

