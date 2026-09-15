# Spectra_test

In this repository I compared the the functions to generate figures of `Spectra`
package. The comparison `plot` vs `ggplot2` on two main points:

- *Installation footprint*: the `ggplot2` method requires more dependencies
  (134 vs 118), but in terms of time it is fairly similar.

- *Rendering of the figures*: all tests are described in the notebook. From
  these tests, I can summarize:
  - `plot` is faster in most cases; it is only slower than `ggplot2` a few
    times, when plotting large figures using `MsBackendMzR`.
  - `ggplot2` handles size limits better. `Base R plot` fails to render the test
    with an unusually high number of spectra (101 spectra plotted using
    `plotSpectra()`).
  - A major advantage of `ggplot2` is its straightforward compatibility with
    `ggiraph` for plot interactivity.
  - `ggplot2` is easier to customize outside the function.

To sum up, `base R plot` is simpler and faster, but it is more difficult to
customize the figures outside the function and to handle interactivity.
`ggplot2` requires more dependencies and is a bit slower, but it is simpler to
customize outside the function and to generate interactive plots.
