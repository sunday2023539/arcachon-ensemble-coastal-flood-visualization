## Visualizing Ensemble Coastal Flood Data in the Arcachon Basin

This repository documents my MSc Applied Geoinformatics internship project at LASTIG / IGN, France (20 April–25 September 2026), carried out in the context of the ORACLES research project. It explores how to communicate coastal flood occurrence and exposed assets along the complex shoreline of the Arcachon Basin.

---
---
**Project overview**

Ensemble flood simulations describe several possible flooding outcomes. Showing those outcomes alongside buildings, roads, railways, waterbodies, and population on a conventional map can make coastal sections difficult to compare. I developed a polar-radial deformation workflow that unwraps a coastal corridor into a continuous strip. The strip provides an overview, while selected sections are enlarged in separate focus maps.

This is an exploratory geovisualization method. The resulting strip is a transformed view for comparison; it is not a geographically scaled substitute for the source map.
---

## Study Area

The study area is the **Arcachon Basin** on the French Atlantic coast.

<img width="667" height="487" alt="image" src="https://github.com/user-attachments/assets/89b45bac-c43e-4598-a11b-25a2a2ea92ac" />

---
---
## Objectives

Represent flood occurrence across ensemble scenarios along the Arcachon Basin coastline.

Compare flood patterns with population and geographic features without overcrowding the map.

Transform and display 27 areas of interest (AOIs) in one continuous coastal view.

Produce an overview strip and more detailed maps of selected coastal sections.

---
---

## Data and tools

The work uses flood simulation outputs supplied through the research project, converted to flood occurrence polygons, plus contextual geographic layers from IGN and OpenStreetMap. A population grid supplies the population values used in the accompanying bar chart.

<img width="842" height="266" alt="image" src="https://github.com/user-attachments/assets/e8e969e4-97c2-46ad-b22e-674dbceffa37" />

---
---

## Method

1. Prepare the coastal corridor: define minimum and maximum control boundaries around the flood-affected coastline and refine the 27 AOIs.

2. Build a radial profile: calculate each location's angle θ and distance r from a chosen centre, together with the boundary distances r_min(θ) and r_max(θ).

3. Unwrap the corridor: normalize radial position as v = (r - r_min(θ)) / (r_max(θ) - r_min(θ)), then map locations to x = θ and y = 1000v.

4. Transform vector features by their vertices: apply the same mapping to flood polygons, AOIs, buildings, transport networks, coastlines, and waterbodies so their shapes remain visible in the strip.

5. Summarize population: aggregate population grid values into 5° angular slices and display them above the strip.

6. Make focus maps: enlarge selected angular sections while retaining the surrounding coastal corridor for context.

Flood occurrence represents the number of ensemble scenarios in which a location is flooded. It should be interpreted with the ensemble size and simulation setup in mind; it is not automatically an annual flood probability.

---
---

## Outputs

Deformation corridor and radial profile: diagnostic views of the control boundaries and transformation.

Transformed flood occurrence and AOIs: flood polygons and 27 AOIs displayed in the same strip coordinates.

Global index strip: a 0°–360° overview combining flood occurrence, population slices, coastline, waterbodies, buildings, roads, and railways.

Focus maps: larger views of selected sections, including 110°–145°, 240°–270°, and 315°–335°. The draft report also marks 5°–20° on the global index.

GIS outputs: transformed vector layers saved as GeoJSON and Shapefile where available.

<img width="1225" height="431" alt="image" src="https://github.com/user-attachments/assets/71eb8551-393b-47a8-8328-ff1b7f64848c" />

---
---

## Interpretation and limitations

The strip helps reveal where flood occurrence and exposed features coincide along the coast. Distances and feature shapes in the deformed view reflect the transformation and any focus-area scaling, so use the original GIS layers for geographic measurement. Small irregularities around the 0°/360° seam and complex coastal sections remain a consideration. The proposed visualization has not yet been validated through formal user testing.

---
---

## Author and context

Babafemi Sunday Olatunji · MSc Applied Geoinformatics, University of Salzburg · Internship at LASTIG / IGN, Paris, France.

This repository presents my individual internship work within the broader ORACLES research context. For full methodological details, see the internship report.




