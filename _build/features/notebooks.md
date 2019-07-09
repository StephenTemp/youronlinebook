---
interact_link: content/features/notebooks.ipynb
kernel_name: python3
has_widgets: false
title: 'Notebooks'
prev_page:
  url: /features/markdown
  title: 'Markdown'
next_page:
  url: /features/features
  title: 'Features'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

<!-- Configure and load Thebe !-->
<script type="text/x-thebe-config">
  {
    requestKernel: true,
    binderOptions: {
      repo: "binder-examples/requirements",
    },
  }
</script>

<script src="https://unpkg.com/thebelab@0.4.0/lib/index.js"></script>

# Content with notebooks

You can also create content with Jupyter Notebooks. The content for the current page is contained
in a Jupyter Notebook in the `notebooks/` folder of the repository. This means that we can include
code blocks and their outputs, and export them to Jekyll markdown.

**You can find the original notebook for this page [at this address](https://github.com/jupyter/jupyter-book/blob/master/jupyter_book/minimal/content/features/notebooks.ipynb)**

## Markdown + notebooks

As it is markdown, you can embed images, HTML, etc into your posts!

![](cool.jpg)

You an also $add_{math}$ and

$$
math^{blocks}
$$

or

$$
\begin{align*}
\mbox{mean} la_{tex} \\ \\
math blocks
\end{align*}
$$

But make sure you \\$Escape \\$your \\$dollar signs \\$you want to keep!

## Code blocks and image outputs

Textbooks with Jupyter will also embed your code blocks and output in your site.
For example, here's some sample Matplotlib code:

<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
print("hello")

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# CLICK ON INTERACT TO EXECUTE THIS CODE SEGMENT WITHOUT ANY ERRORS

import numpy as np
from bokeh.plotting import figure, show
from bokeh.io import output_notebook

N = 4000
x = np.random.random(size=N) * 100
y = np.random.random(size=N) * 100
radii = np.random.random(size=N) * 1.5
colors = ["#%02d%02d%02d" % (r, g, 150) for r, g in zip(np.floor(50+2*x), np.floor(30+2*y))]
output_notebook()
p = figure()
p.circle(x, y, radius=radii, fill_color=colors, fill_alpha=0.6, line_color=None)
show(p)

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
from matplotlib import rcParams, cycler
import matplotlib.pyplot as plt
import numpy as np
plt.ion()

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# Fixing random state for reproducibility
np.random.seed(19680801)

N = 10
data = [np.logspace(0, 1, 100) + np.random.randn(100) + ii for ii in range(N)]
data = np.array(data).T
cmap = plt.cm.coolwarm
rcParams['axes.prop_cycle'] = cycler(color=cmap(np.linspace(0, 1, N)))


from matplotlib.lines import Line2D
custom_lines = [Line2D([0], [0], color=cmap(0.), lw=4),
                Line2D([0], [0], color=cmap(.5), lw=4),
                Line2D([0], [0], color=cmap(1.), lw=4)]

fig, ax = plt.subplots(figsize=(10, 5))
lines = ax.plot(data)
ax.legend(custom_lines, ['Cold', 'Medium', 'Hot']);

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

{:.output_png}
![png](../images/features/notebooks_4_0.png)

</div>
</div>
</div>



Note that the image above is captured and displayed by Jekyll.



## Removing content before publishing

You can also remove some content before publishing your book to the web. For example,
in [the original notebook](https://github.com/jupyter/jupyter-book/blob/master/jupyter_book/minimal/content/features/notebooks.ipynb) there
used to be a cell below...



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
thisvariable = "none of this should show up in the textbook"

fig, ax = plt.subplots()
x = np.random.randn(100)
y = np.random.randn(100)
ax.scatter(x, y, s=np.abs(x*100), c=x, cmap=plt.cm.coolwarm)
ax.text(0, .5, thisvariable, fontsize=20, transform=ax.transAxes)
ax.set_axis_off()

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

{:.output_png}
![png](../images/features/notebooks_7_0.png)

</div>
</div>
</div>



You can also **remove only the code** so that images and other output still show up.

Below we'll *only* display an image. It was generated with Python code in a cell,
which you can [see in the original notebook](https://github.com/jupyter/jupyter-book/blob/master/jupyter_book/minimal/content/features/notebooks.ipynb)



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# NO CODE
thisvariable = "this plot *will* show up in the textbook."

fig, ax = plt.subplots()
x = np.random.randn(100)
y = np.random.randn(100)
ax.scatter(x, y, s=np.abs(x*100), c=x, cmap=plt.cm.coolwarm)
ax.text(0, .5, thisvariable, fontsize=20, transform=ax.transAxes)
ax.set_axis_off()

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">

{:.output_png}
![png](../images/features/notebooks_9_0.png)

</div>
</div>
</div>



And here we'll *only* display a Pandas DataFrame. Again, this was generated with Python code
from [this original notebook](https://github.com/jupyter/jupyter-book/blob/master/jupyter_book/minimal/content/features/notebooks.ipynb).



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
# NO CODE
import pandas as pd
pd.DataFrame([['hi', 'there'], ['this', 'is'], ['a', 'DataFrame']], columns=['Word A', 'Word B'])

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">



<div markdown="0" class="output output_html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Word A</th>
      <th>Word B</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>hi</td>
      <td>there</td>
    </tr>
    <tr>
      <th>1</th>
      <td>this</td>
      <td>is</td>
    </tr>
    <tr>
      <th>2</th>
      <td>a</td>
      <td>DataFrame</td>
    </tr>
  </tbody>
</table>
</div>
</div>


</div>
</div>
</div>



You can configure the text that *Textbooks with Jupyter* uses for this by modifying your site's `_config.yml` file.



## Interactive outputs

We can even do the same for *interactive* material. Below we'll display a map using `ipyleaflet`. When the notebook
is converted to Markdown, the code for creating the interactive map is retained.

**Note that this will only work for some packages.** They need to be able to output standalone HTML/Javascript, and not
depend on an underlying Python kernel to work.



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
import folium

```
</div>

</div>



<div markdown="1" class="cell code_cell">
<div class="input_area" markdown="1">
```python
m = folium.Map(
    location=[45.372, -121.6972],
    zoom_start=12,
    tiles='Stamen Terrain'
)

folium.Marker(
    location=[45.3288, -121.6625],
    popup='Mt. Hood Meadows',
    icon=folium.Icon(icon='cloud')
).add_to(m)

folium.Marker(
    location=[45.3311, -121.7113],
    popup='Timberline Lodge',
    icon=folium.Icon(color='green')
).add_to(m)

folium.Marker(
    location=[45.3300, -121.6823],
    popup='Some Other Location',
    icon=folium.Icon(color='red', icon='info-sign')
).add_to(m)


m

```
</div>

<div class="output_wrapper" markdown="1">
<div class="output_subarea" markdown="1">



<div markdown="0" class="output output_html">
<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><iframe src="data:text/html;charset=utf-8;base64,PCFET0NUWVBFIGh0bWw+CjxoZWFkPiAgICAKICAgIDxtZXRhIGh0dHAtZXF1aXY9ImNvbnRlbnQtdHlwZSIgY29udGVudD0idGV4dC9odG1sOyBjaGFyc2V0PVVURi04IiAvPgogICAgCiAgICAgICAgPHNjcmlwdD4KICAgICAgICAgICAgTF9OT19UT1VDSCA9IGZhbHNlOwogICAgICAgICAgICBMX0RJU0FCTEVfM0QgPSBmYWxzZTsKICAgICAgICA8L3NjcmlwdD4KICAgIAogICAgPHNjcmlwdCBzcmM9Imh0dHBzOi8vY2RuLmpzZGVsaXZyLm5ldC9ucG0vbGVhZmxldEAxLjQuMC9kaXN0L2xlYWZsZXQuanMiPjwvc2NyaXB0PgogICAgPHNjcmlwdCBzcmM9Imh0dHBzOi8vY29kZS5qcXVlcnkuY29tL2pxdWVyeS0xLjEyLjQubWluLmpzIj48L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL21heGNkbi5ib290c3RyYXBjZG4uY29tL2Jvb3RzdHJhcC8zLjIuMC9qcy9ib290c3RyYXAubWluLmpzIj48L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2NkbmpzLmNsb3VkZmxhcmUuY29tL2FqYXgvbGlicy9MZWFmbGV0LmF3ZXNvbWUtbWFya2Vycy8yLjAuMi9sZWFmbGV0LmF3ZXNvbWUtbWFya2Vycy5qcyI+PC9zY3JpcHQ+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIGhyZWY9Imh0dHBzOi8vY2RuLmpzZGVsaXZyLm5ldC9ucG0vbGVhZmxldEAxLjQuMC9kaXN0L2xlYWZsZXQuY3NzIi8+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIGhyZWY9Imh0dHBzOi8vbWF4Y2RuLmJvb3RzdHJhcGNkbi5jb20vYm9vdHN0cmFwLzMuMi4wL2Nzcy9ib290c3RyYXAubWluLmNzcyIvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL21heGNkbi5ib290c3RyYXBjZG4uY29tL2Jvb3RzdHJhcC8zLjIuMC9jc3MvYm9vdHN0cmFwLXRoZW1lLm1pbi5jc3MiLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9mb250LWF3ZXNvbWUvNC42LjMvY3NzL2ZvbnQtYXdlc29tZS5taW4uY3NzIi8+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIGhyZWY9Imh0dHBzOi8vY2RuanMuY2xvdWRmbGFyZS5jb20vYWpheC9saWJzL0xlYWZsZXQuYXdlc29tZS1tYXJrZXJzLzIuMC4yL2xlYWZsZXQuYXdlc29tZS1tYXJrZXJzLmNzcyIvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL3Jhd2Nkbi5naXRoYWNrLmNvbS9weXRob24tdmlzdWFsaXphdGlvbi9mb2xpdW0vbWFzdGVyL2ZvbGl1bS90ZW1wbGF0ZXMvbGVhZmxldC5hd2Vzb21lLnJvdGF0ZS5jc3MiLz4KICAgIDxzdHlsZT5odG1sLCBib2R5IHt3aWR0aDogMTAwJTtoZWlnaHQ6IDEwMCU7bWFyZ2luOiAwO3BhZGRpbmc6IDA7fTwvc3R5bGU+CiAgICA8c3R5bGU+I21hcCB7cG9zaXRpb246YWJzb2x1dGU7dG9wOjA7Ym90dG9tOjA7cmlnaHQ6MDtsZWZ0OjA7fTwvc3R5bGU+CiAgICAKICAgICAgICAgICAgPG1ldGEgbmFtZT0idmlld3BvcnQiIGNvbnRlbnQ9IndpZHRoPWRldmljZS13aWR0aCwKICAgICAgICAgICAgICAgIGluaXRpYWwtc2NhbGU9MS4wLCBtYXhpbXVtLXNjYWxlPTEuMCwgdXNlci1zY2FsYWJsZT1ubyIgLz4KICAgICAgICAgICAgPHN0eWxlPgogICAgICAgICAgICAgICAgI21hcF8xNThhMTdhZmEwZDY0YTIyODYyMzFiNmFjNzU2N2RjNSB7CiAgICAgICAgICAgICAgICAgICAgcG9zaXRpb246IHJlbGF0aXZlOwogICAgICAgICAgICAgICAgICAgIHdpZHRoOiAxMDAuMCU7CiAgICAgICAgICAgICAgICAgICAgaGVpZ2h0OiAxMDAuMCU7CiAgICAgICAgICAgICAgICAgICAgbGVmdDogMC4wJTsKICAgICAgICAgICAgICAgICAgICB0b3A6IDAuMCU7CiAgICAgICAgICAgICAgICB9CiAgICAgICAgICAgIDwvc3R5bGU+CiAgICAgICAgCjwvaGVhZD4KPGJvZHk+ICAgIAogICAgCiAgICAgICAgICAgIDxkaXYgY2xhc3M9ImZvbGl1bS1tYXAiIGlkPSJtYXBfMTU4YTE3YWZhMGQ2NGEyMjg2MjMxYjZhYzc1NjdkYzUiID48L2Rpdj4KICAgICAgICAKPC9ib2R5Pgo8c2NyaXB0PiAgICAKICAgIAogICAgICAgICAgICB2YXIgbWFwXzE1OGExN2FmYTBkNjRhMjI4NjIzMWI2YWM3NTY3ZGM1ID0gTC5tYXAoCiAgICAgICAgICAgICAgICAibWFwXzE1OGExN2FmYTBkNjRhMjI4NjIzMWI2YWM3NTY3ZGM1IiwKICAgICAgICAgICAgICAgIHsKICAgICAgICAgICAgICAgICAgICBjZW50ZXI6IFs0NS4zNzIsIC0xMjEuNjk3Ml0sCiAgICAgICAgICAgICAgICAgICAgY3JzOiBMLkNSUy5FUFNHMzg1NywKICAgICAgICAgICAgICAgICAgICB6b29tOiAxMiwKICAgICAgICAgICAgICAgICAgICB6b29tQ29udHJvbDogdHJ1ZSwKICAgICAgICAgICAgICAgICAgICBwcmVmZXJDYW52YXM6IGZhbHNlLAogICAgICAgICAgICAgICAgfQogICAgICAgICAgICApOwoKICAgICAgICAgICAgCgogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciB0aWxlX2xheWVyXzA2N2RkMTI4MGUwYTRiNDA4ZjM0NTg5YzU0OWE3M2RmID0gTC50aWxlTGF5ZXIoCiAgICAgICAgICAgICAgICAiaHR0cHM6Ly9zdGFtZW4tdGlsZXMte3N9LmEuc3NsLmZhc3RseS5uZXQvdGVycmFpbi97en0ve3h9L3t5fS5qcGciLAogICAgICAgICAgICAgICAgeyJhdHRyaWJ1dGlvbiI6ICJNYXAgdGlsZXMgYnkgXHUwMDNjYSBocmVmPVwiaHR0cDovL3N0YW1lbi5jb21cIlx1MDAzZVN0YW1lbiBEZXNpZ25cdTAwM2MvYVx1MDAzZSwgdW5kZXIgXHUwMDNjYSBocmVmPVwiaHR0cDovL2NyZWF0aXZlY29tbW9ucy5vcmcvbGljZW5zZXMvYnkvMy4wXCJcdTAwM2VDQyBCWSAzLjBcdTAwM2MvYVx1MDAzZS4gRGF0YSBieSBcdTAwMjZjb3B5OyBcdTAwM2NhIGhyZWY9XCJodHRwOi8vb3BlbnN0cmVldG1hcC5vcmdcIlx1MDAzZU9wZW5TdHJlZXRNYXBcdTAwM2MvYVx1MDAzZSwgdW5kZXIgXHUwMDNjYSBocmVmPVwiaHR0cDovL2NyZWF0aXZlY29tbW9ucy5vcmcvbGljZW5zZXMvYnktc2EvMy4wXCJcdTAwM2VDQyBCWSBTQVx1MDAzYy9hXHUwMDNlLiIsICJkZXRlY3RSZXRpbmEiOiBmYWxzZSwgIm1heE5hdGl2ZVpvb20iOiAxOCwgIm1heFpvb20iOiAxOCwgIm1pblpvb20iOiAwLCAibm9XcmFwIjogZmFsc2UsICJvcGFjaXR5IjogMSwgInN1YmRvbWFpbnMiOiAiYWJjIiwgInRtcyI6IGZhbHNlfQogICAgICAgICAgICApLmFkZFRvKG1hcF8xNThhMTdhZmEwZDY0YTIyODYyMzFiNmFjNzU2N2RjNSk7CiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIG1hcmtlcl82YzI5NDk4MjZkZTg0MzMxOWZlMmMyMDAxODE3MmNjNyA9IEwubWFya2VyKAogICAgICAgICAgICAgICAgWzQ1LjMyODgsIC0xMjEuNjYyNV0sCiAgICAgICAgICAgICAgICB7fQogICAgICAgICAgICApLmFkZFRvKG1hcF8xNThhMTdhZmEwZDY0YTIyODYyMzFiNmFjNzU2N2RjNSk7CiAgICAgICAgCiAgICAKICAgICAgICAgICAgdmFyIGljb25fMGQxZDc0ZDAzY2I1NDVlNGI1ZGNhNzkzMzI4ZmRjYWEgPSBMLkF3ZXNvbWVNYXJrZXJzLmljb24oCiAgICAgICAgICAgICAgICB7ImV4dHJhQ2xhc3NlcyI6ICJmYS1yb3RhdGUtMCIsICJpY29uIjogImNsb3VkIiwgImljb25Db2xvciI6ICJ3aGl0ZSIsICJtYXJrZXJDb2xvciI6ICJibHVlIiwgInByZWZpeCI6ICJnbHlwaGljb24ifQogICAgICAgICAgICApOwogICAgICAgICAgICBtYXJrZXJfNmMyOTQ5ODI2ZGU4NDMzMTlmZTJjMjAwMTgxNzJjYzcuc2V0SWNvbihpY29uXzBkMWQ3NGQwM2NiNTQ1ZTRiNWRjYTc5MzMyOGZkY2FhKTsKICAgICAgICAKICAgIAogICAgICAgIHZhciBwb3B1cF9lYWQ4ODc2ZjM3NDk0MDIxYjUxNDE3NjRhODZhNjg0YSA9IEwucG9wdXAoeyJtYXhXaWR0aCI6ICIxMDAlIn0pOwoKICAgICAgICAKICAgICAgICAgICAgdmFyIGh0bWxfYmJjMzQzNTc5YWFhNGIzYmFjNzdkNzUwZWUxMTg0MGUgPSAkKGA8ZGl2IGlkPSJodG1sX2JiYzM0MzU3OWFhYTRiM2JhYzc3ZDc1MGVlMTE4NDBlIiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5NdC4gSG9vZCBNZWFkb3dzPC9kaXY+YClbMF07CiAgICAgICAgICAgIHBvcHVwX2VhZDg4NzZmMzc0OTQwMjFiNTE0MTc2NGE4NmE2ODRhLnNldENvbnRlbnQoaHRtbF9iYmMzNDM1NzlhYWE0YjNiYWM3N2Q3NTBlZTExODQwZSk7CiAgICAgICAgCgogICAgICAgIG1hcmtlcl82YzI5NDk4MjZkZTg0MzMxOWZlMmMyMDAxODE3MmNjNy5iaW5kUG9wdXAocG9wdXBfZWFkODg3NmYzNzQ5NDAyMWI1MTQxNzY0YTg2YTY4NGEpCiAgICAgICAgOwoKICAgICAgICAKICAgIAogICAgCiAgICAgICAgICAgIHZhciBtYXJrZXJfZjY2MTIzOGNmYTQ3NDcxZWI3ODVhNjBhMDdmYzMwZjIgPSBMLm1hcmtlcigKICAgICAgICAgICAgICAgIFs0NS4zMzExLCAtMTIxLjcxMTNdLAogICAgICAgICAgICAgICAge30KICAgICAgICAgICAgKS5hZGRUbyhtYXBfMTU4YTE3YWZhMGQ2NGEyMjg2MjMxYjZhYzc1NjdkYzUpOwogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciBpY29uXzczZGNmYjhlMmVlNTQyZTZhYjE5YzRlMDE4NjVkNjRjID0gTC5Bd2Vzb21lTWFya2Vycy5pY29uKAogICAgICAgICAgICAgICAgeyJleHRyYUNsYXNzZXMiOiAiZmEtcm90YXRlLTAiLCAiaWNvbiI6ICJpbmZvLXNpZ24iLCAiaWNvbkNvbG9yIjogIndoaXRlIiwgIm1hcmtlckNvbG9yIjogImdyZWVuIiwgInByZWZpeCI6ICJnbHlwaGljb24ifQogICAgICAgICAgICApOwogICAgICAgICAgICBtYXJrZXJfZjY2MTIzOGNmYTQ3NDcxZWI3ODVhNjBhMDdmYzMwZjIuc2V0SWNvbihpY29uXzczZGNmYjhlMmVlNTQyZTZhYjE5YzRlMDE4NjVkNjRjKTsKICAgICAgICAKICAgIAogICAgICAgIHZhciBwb3B1cF82OWM4ZTQ1YTgzNWY0Y2I4YjAzOWRjNThmNDg0YTk4MiA9IEwucG9wdXAoeyJtYXhXaWR0aCI6ICIxMDAlIn0pOwoKICAgICAgICAKICAgICAgICAgICAgdmFyIGh0bWxfYjQ1ZjUxYWQ1NzUyNDYwZWFhYjhhMjY3YzdkZmViYzUgPSAkKGA8ZGl2IGlkPSJodG1sX2I0NWY1MWFkNTc1MjQ2MGVhYWI4YTI2N2M3ZGZlYmM1IiBzdHlsZT0id2lkdGg6IDEwMC4wJTsgaGVpZ2h0OiAxMDAuMCU7Ij5UaW1iZXJsaW5lIExvZGdlPC9kaXY+YClbMF07CiAgICAgICAgICAgIHBvcHVwXzY5YzhlNDVhODM1ZjRjYjhiMDM5ZGM1OGY0ODRhOTgyLnNldENvbnRlbnQoaHRtbF9iNDVmNTFhZDU3NTI0NjBlYWFiOGEyNjdjN2RmZWJjNSk7CiAgICAgICAgCgogICAgICAgIG1hcmtlcl9mNjYxMjM4Y2ZhNDc0NzFlYjc4NWE2MGEwN2ZjMzBmMi5iaW5kUG9wdXAocG9wdXBfNjljOGU0NWE4MzVmNGNiOGIwMzlkYzU4ZjQ4NGE5ODIpCiAgICAgICAgOwoKICAgICAgICAKICAgIAogICAgCiAgICAgICAgICAgIHZhciBtYXJrZXJfOTE1YzJmYzI0MmFhNDIwMzg0NWQ3N2FhZGZiMzI1NTMgPSBMLm1hcmtlcigKICAgICAgICAgICAgICAgIFs0NS4zMywgLTEyMS42ODIzXSwKICAgICAgICAgICAgICAgIHt9CiAgICAgICAgICAgICkuYWRkVG8obWFwXzE1OGExN2FmYTBkNjRhMjI4NjIzMWI2YWM3NTY3ZGM1KTsKICAgICAgICAKICAgIAogICAgICAgICAgICB2YXIgaWNvbl8yMDM0N2I2YTgxZDA0YjExYTI3OTRkMGM1ZmQzYmQ4YSA9IEwuQXdlc29tZU1hcmtlcnMuaWNvbigKICAgICAgICAgICAgICAgIHsiZXh0cmFDbGFzc2VzIjogImZhLXJvdGF0ZS0wIiwgImljb24iOiAiaW5mby1zaWduIiwgImljb25Db2xvciI6ICJ3aGl0ZSIsICJtYXJrZXJDb2xvciI6ICJyZWQiLCAicHJlZml4IjogImdseXBoaWNvbiJ9CiAgICAgICAgICAgICk7CiAgICAgICAgICAgIG1hcmtlcl85MTVjMmZjMjQyYWE0MjAzODQ1ZDc3YWFkZmIzMjU1My5zZXRJY29uKGljb25fMjAzNDdiNmE4MWQwNGIxMWEyNzk0ZDBjNWZkM2JkOGEpOwogICAgICAgIAogICAgCiAgICAgICAgdmFyIHBvcHVwXzcwZmI5YWVlZTE1MzRjN2ViN2U5NjhlMTVjMGU4NGQ1ID0gTC5wb3B1cCh7Im1heFdpZHRoIjogIjEwMCUifSk7CgogICAgICAgIAogICAgICAgICAgICB2YXIgaHRtbF84ZGRjNDZkNjZlNjE0NzZjYTM3MTNhYTFiZTc4MjI5NyA9ICQoYDxkaXYgaWQ9Imh0bWxfOGRkYzQ2ZDY2ZTYxNDc2Y2EzNzEzYWExYmU3ODIyOTciIHN0eWxlPSJ3aWR0aDogMTAwLjAlOyBoZWlnaHQ6IDEwMC4wJTsiPlNvbWUgT3RoZXIgTG9jYXRpb248L2Rpdj5gKVswXTsKICAgICAgICAgICAgcG9wdXBfNzBmYjlhZWVlMTUzNGM3ZWI3ZTk2OGUxNWMwZTg0ZDUuc2V0Q29udGVudChodG1sXzhkZGM0NmQ2NmU2MTQ3NmNhMzcxM2FhMWJlNzgyMjk3KTsKICAgICAgICAKCiAgICAgICAgbWFya2VyXzkxNWMyZmMyNDJhYTQyMDM4NDVkNzdhYWRmYjMyNTUzLmJpbmRQb3B1cChwb3B1cF83MGZiOWFlZWUxNTM0YzdlYjdlOTY4ZTE1YzBlODRkNSkKICAgICAgICA7CgogICAgICAgIAogICAgCjwvc2NyaXB0Pg==" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>
</div>


</div>
</div>
</div>

