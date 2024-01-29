1. all the assets such as icons used are prsent in the Assets folder
2. CSV, XLSX files and other datasets used for the visualization purposes are stored in the Datasets folder
3. Current main working Jupyter notebook is Univariate_4_charts

Univariate_4_charts structure:
  1. data preprocessing: cleaning missing values, removing points outside the bounds of Chicago
  2. spatial operations: preprocessing spatial operations are performed on the datasets by converting them into geodataframes
  3. VEGALITE: we use vegalite framework inside jupyter notebook for easy access to preprocessing as well as visualization tasks
  4. the general vegalite structure + jupyter is :
      spec = { [VEGALITE SPEC. (example:https://vega.github.io/vega-lite/examples/bar.html) }
      display(alt.display.html_renderer(spec), raw=True)
 6. the processed geodataframes needs to be converted to be compatible with Vegalite spec in the following format :
    income_pop_json = income_pop_gdf.to_json() //convert the geodataframe into JSON string
    income_pop_geojson = json.loads(income_pop_json)      //convert the JSON string into python object to be used in vegalite spec
  7. Bivariate Charts are generated using choropleth charts in vegalite asa workaround. We assign colours based on the ranges which falls in a 3x3 grid.


