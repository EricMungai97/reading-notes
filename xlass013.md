# Matplotlib Tutorial

Matplotlib is most used package for 2 D graphics.

It enables one to visualize data from Python and publication-quality figures in many formats.

`Ipython`  is an enhanced interactive Python shell that has lots of interesting features including named inputs and outputs, access to shell commands, improved debugging and much more. It allows interactive matplotlib sessions that have Matlab/Mathematica-like functionality.

`Pyplot` provides a convenient interface to the matplotlib object-oriented plotting library.

**Pyplot Tutorial**

```
import matplotlib.pyplot as plt
plt.plot([1,2,3,4])
plt.ylabel('some numbers')
plt.show()
```
![Plot Image](/images/plot_simple.png)

Matplotlib comes with a set of default settings that allow customizing all kinds of properties. You can control the defaults of almost every property in matplotlib: `figure size` and `dpi`, `line width`, `color` and `style`, `axes`, `axis` and `grid` properties, `text` and `font properties` and so on. While matplotlib defaults are rather good in most cases, you may want to modify some properties for specific cases.

## Seaborn

Seaborn is a library for making statistical graphics in Python. It builds on top of matplotlib and integrates closely with pandas data structures.

Its plotting functions operate on dataframes and arrays containing whole datasets and internally perform the necessary semantic mapping and statistical aggregation to produce informative plots. Its dataset-oriented, declarative API lets you focus on what the different elements of your plots mean, rather than on the details of how to draw them.

Example code

```
# Import seaborn
import seaborn as sns

# Apply the default theme
sns.set_theme()

# Load an example dataset
tips = sns.load_dataset("tips")

# Create a visualization
sns.relplot(
    data=tips,
    x="total_bill", y="tip", col="time",
    hue="smoker", style="smoker", size="size",
)
```

![Outcome](/images/outcome.png)

Behind the scenes, seaborn uses `matplotlib`to draw its plots.