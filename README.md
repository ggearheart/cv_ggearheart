## My pagedown rendered CV

> NOTE: This repo adapts and lightly modifies [Nick Strayer's (very impressive and aesthetic) CV](https://github.com/nstrayer/cv).

This repo contains the source-code and results of my CV built with the [pagedown package](https://pagedown.rbind.io) and a modified version of the 'resume' template. 

The main files are:

- `index.Rmd`: Source template for the cv, contains a variable `PDF_EXPORT` in the header that changes styles for pdf vs html. To export a PDF, knit an html with `PDF_EXPORT <- FALSE`, then print the page, save, and ensure background graphics are turned on (the same goes for the PDF 1-pg resume).  
- `index.html`: The final output of the template when the header variable `PDF_EXPORT` is set to `FALSE`. View it at [richpauloo.com/cv](http://richpauloo.com/cv).
- `pauloo_cv.pdf`: The final exported pdf as rendered by Chrome on my mac laptop. Links are put in footer and notes about online version are added. 
- `resume.Rmd`: Source template for single page resume. 
- `pauloo_resume.pdf`: Result for single page resume.
- `positions.csv`: A csv with columns encoding the various fields needed for a position entry in the CV. A column `section` is also available so different sections know which rows to use.
- `css/`: Directory containing the custom CSS files used to tweak the default 'resume' format from pagedown. 

## Want to use this to build your own CV/resume? 

1. Fork, clone, download the zip of this repo to your machine with RStudio.
2. Go through and personalize the supplementary text in the Rmd you desire (`index.Rmd` for CV, `resume.Rmd` for resume).
3. Using your spreadsheet editor of choice, replace the rows of `positions.csv` with your positions.
3. Print each unique `section` (as encoded in the `section` column of `positions.csv`) in your `.Rmd` with the command `position_data %>% print_section('education')`.
