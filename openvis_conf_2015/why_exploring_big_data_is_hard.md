## Why exploring big data is hard (and what we can do about it)

### Danyel Fisher

__Summary:__
Exploring data freely lets you find unexpected patterns and shapes -- but it's hard to explore really big datasets. It takes a lot of computing, network, and disk power to squeeze a few trillion records into a million pixels quickly enough to see anything interesting. There are a lot of approaches out there, from throwing bigger clusters at the problem, to indexing more aggressively. In this talk, Danyel is going to discuss several different approaches to big data visualization that will allow data scientists to more freely explore and analyze unwieldy data.

---

* the size of the dataset is part of the problem

* representation: what visualizations are suitable for big data?
* interaction: what interactions should be allowed for exploration?

#### aggregation

* what is the aggregation equivalent of a bar graph?
* what is the aggregated equivalent of a scatterplot, or line-graph?

#### generalized histograms

* select buckets on data ->
* examine points, placing them into bukcets ->
* create shapes based on buckets
