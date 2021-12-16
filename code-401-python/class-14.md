# Data Visualization using Matplotlib

[Source: gh @rougier matplotlib-tutorial](https://github.com/rougier/matplotlib-tutorial#animation)

**matplotlib** is one of the most widely used Python packages for 2D-graphics. It can quickly visualize data with various figure formats.

**pyplot** allows for object-oriented control of matplotlib commands, and is used to control a plot.

## Defaults

matplotlib comes with certain default settings that will be utilized if we just use `plt.plot()` without optional arguments. Default values can be instantiated (such as `plt.figure`, `plt.xlim`, etc.) to modify the plot and save us from repeating ourselves if we have a common desired plot format.

## Figures, Subplots, Axes, Ticks

**Figures** are the windows through which the GUI displays. Figures are numbered starting at 1 (not 0). They have the following parameters:

* num - the figure number
* figsize - the figure size in inches
* dpi - resolution in dots per inch
* facecolor - color of the background
* edgecolor - color of edge around background
* frameon - boolean of whether to draw frame

**Subplot(rows, columns, plotnum)** can arrange plots in a grid within a drawing.

**Axes** are similar to subplot but allow placement anywhere within the drawing. This can be useful for layering plots over one another.

**Ticks** are how we understand our x and y axis on a plot. matplotlib has fully configurable tick settings.

## Animation

As of 1.1, matplotlib includes tools for intuitively creating animations. This is accomplished using an update function to continuously modify the data of matplotlib.

```Python
#From tutorial:

def update(frame):
    global P, C, S

    # Every ring is made more transparent
    C[:,3] = np.maximum(0, C[:,3] - 1.0/n)

    # Each ring is made larger
    S += (size_max - size_min) / n

    # Reset ring specific ring (relative to frame number)
    i = frame % 50
    P[i] = np.random.uniform(0,1,2)
    S[i] = size_min
    C[i,3] = 1

    # Update scatter object
    scat.set_edgecolors(C)
    scat.set_sizes(S)
    scat.set_offsets(P)

    # Return the modified object
    return scat,


animation = FuncAnimation(fig, update, interval=10, blit=True, frames=200)
# animation.save('rain.gif', writer='imagemagick', fps=30, dpi=40)
plt.show()
```

## Other plots

matplotlib has capability for many plots:

* Regular
* Scatter
* Bar
* Contour
* Imshow (display image)
* Quiver (field of arrows)
* Pie Chart
* Grid
* Polar axis
* 3D
* Text
* And more!
