# ESPM 154 Lab 9

Upload the contents of this folder to the course GitHub repository. Keep the Rmd
and support/ directory together. Students should open ESPM154_Lab9.Rmd in DataHub
RStudio with the repository folder as their working directory (an RStudio Project
can set this automatically).

Run the notebook chunks in order. Shiny draws all three landscapes simultaneously.
The five buttons beneath each map paint 0, 0.25, 0.5, 0.75, or 1. Save closes the
editor and returns R matrices. A disconnected editor page after Save is normal;
return to RStudio. Drawings are saved under landscapes/.

Simulations run sequentially from R using a separate Python process. Wait for
each simulation chunk to finish before running subsequent chunks. There is no
background-job workflow or reticulate integration. The model uses 1,000 total
loci and starts with 500 individuals before burn-in. Recombination-cache settings
remain the original values. These simulation settings completed 200 steps in
Ian's DataHub RStudio test; the newly added VCF export still needs an end-to-end
DataHub check before distribution.

The parameter chunk shows the actual template's starting population and total
loci, plus editable selection, trait-locus, capacity, movement, mating, and seed
settings. Each run_geonomics() call starts a fresh model. steps=c(100,100) walks
the same model through two consecutive stages. Step 0 is after burn-in.

Each run folder contains input landscapes, logs, stages.csv, result.rds, and at
all saved stages: stage_XX.vcf, stage_XX_individuals.csv,
stage_XX_coordinates.csv, and stage_XX_dosage.csv.gz. VCFs include fixed loci.
Match coordinates and VCF samples by individual ID. Coordinates are in grid units.
PCA is refitted per stage; PC signs and colors may change between plots.

Required R packages: shiny, jsonlite, knitr, rmarkdown. The DataHub Python
interpreter is /srv/conda/envs/notebook/bin/python with Geonomics installed.
No evodoodle Python package, Pygame, ipycanvas, or processx is required.

Run interactive chunks individually before knitting. Knit reuses the student's
own saved landscapes and results. To reuse results interactively, use rerun=FALSE;
to reuse drawings, use redraw=FALSE. Keep landscapes/ and runs/ locally when
submitting or reopening completed work. They are excluded from Git by .gitignore.
R result objects contain relative run paths; open them from the project folder.

The template derives from Anusha Bishop's MIT-licensed Evodoodle (2024), commit
b7e98ae0c6d19fc545972e7c5897d45b6c04d4e0. The license is in support/.
