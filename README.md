# OSolar Web Mapping

This is the home for my initial attempts at creating a web map for my OSolar project.

## Checklist

Let's put the ducks in a row. How do we actually get to creating a prototype?

- [ ] Get some map layers prepared.
    - [ ] Collect the layers from the MGEM project.
    - [ ] Reformat them into tiles (PMTiles and COG).
- [ ] Create a map to load layers into.

## Roadmap

1. **Static Prototype**. The first product created in this repo will be a static map visualizing the results from my capstone project. This will be a 2-metre spatial resolution.
2. **Static Improvement**. The second product will be a copy of the first... But with an improvement in spatial resolution!
3. **Dynamic Interface**. Finally, we attempt to make the web-app dynamic. This will involve switching over to [TiTiler](https://developmentseed.org/titiler/) and [Martin](https://martin.maplibre.org/) to enable some really cool functionality (e.g. integrating zoning, customizeable cutoffs, etc.).