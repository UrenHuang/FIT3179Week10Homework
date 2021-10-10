{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "width": 600,
  "height": 500,
  "title": "Active cases of COVID-19 in various countries",
  "data": {
    "url": "https://raw.githubusercontent.com/UrenHuang/FIT3179Week10Homework/main/worldometer_data.csv"},
  "params": [ 
    {
      "name": "ActiveCases_Above", 
      "value": 0,
      "bind": { 
        "input": "range",
        "min": 0, 
        "max": 300000, 
        "step": 1, 
        "name": "ActiveCases: " 
      }
    },
    { 
      "name": "Continent_selection", 
      "bind": { 
        "input": "select", 
        "options": [ 
          null,
          "Africa", 
          "Asia", 
          "Europe", 
          "Oceania",
          "North America", 
          "South America"
        ], 
        "labels":[
          "Show all",
          "Africa", 
          "Asia", 
          "Europe", 
          "Oceania",
          "North America", 
          "South America"
        ], 
        "name": "Select the continent to display: " 
      } 
    } 
  ],

  "transform": [
    {"filter": "datum.ActiveCases > 0"}, 
    {"filter": "datum.Population > 0"},
    {"filter": "datum.ActiveCases > ActiveCases_Above"},
    {"filter": "Continent_selection == null || datum.Continent == Continent_selection"}
  ],
  "encoding": {
    "x": { 
      "field": "Population", 
      "type": "quantitative", 
      "title": "The population of a country",
      "axis": {"tickCount":10},
      "scale":{"type": "log", "domain":[1,10000000000]}
    }, 
    "y": { 
      "field": "ActiveCases", 
      "type": "quantitative",
      "title": "Number of active cases",
      "axis": {"tickCount":6},
      "scale":{"type": "log", "domain":[1,10000000]}
     }
    }, 
    "layer": [ 
      { 
        "selection": { 
          "continent_highlight":{ 
            "type": "multi", 
            "fields": ["Continent"], 
            "bind": "legend" 
          } 
        },
        "mark": "circle",
        "encoding": {
          "size": { 
            "field": "ActiveCases", 
            "type": "quantitative",
            "scale":{
            "type":"threshold",
            "domain":[50, 200, 500, 1000, 1500, 2000],
            "range":[10, 50, 150, 200, 300, 400, 500]
      },
      "legend": {"format":".1s"}
    },
    "color": { 
        "field": "Continent", 
        "type": "nominal",
        "scale": { 
          "domain": [ 
            "Africa", 
            "Asia", 
            "Europe", 
            "Oceania",
            "North America", 
            "South America"
          ],
          "range": [ 
            "#80b1d3", 
            "#fdb462", 
            "#b2df8a", 
            "#fb8072", 
            "#bebada", 
            "#8dd3c7" 
          ] 
        }
      }, 
      "opacity": { 
         "condition": {"selection": "continent_highlight", "value": 0.8},
      "value": 0.1
    },
    "tooltip":[
          {"field": "Country", "type": "nominal"}, 
          {"field": "Continent", "type": "nominal"}, 
          {"field": "Population", "type": "quantitative", "format": ","}, 
          {"field": "TotalTests", "type": "quantitative", "format": ","}, 
          {"field": "ActiveCases", "type": "quantitative"}
          
        ]
      } 
    },
    {
      "mark":{
        "type": "text", 
        "align": "right", 
        "baseline": "middle", 
        "dx": -11, 
        "fontSize": 10,
        "fontStyle": "Calibri"
        
      },
      "encoding": {
        "text": {"field": "Country", "type": "nominal"}, 
        "color": {"value": "black"},
        "opacity": { 
          "condition": { 
            "test": "datum['Country'] == 'India' || datum['Country'] == 'USA' || datum['Country'] == 'New Zealand' || datum['Country'] == 'Thailand' || datum['Country'] == 'France'", 
            "value": 0.8
          },
      "value": 0
    },
  
    "tooltip":[
          {"field": "Country", "type": "nominal"}, 
          {"field": "Continent", "type": "nominal"}, 
          {"field": "Population", "type": "quantitative", "format": ","}, 
          {"field": "TotalTests", "type": "quantitative", "format": ","}, 
          {"field": "ActiveCases", "type": "quantitative"}
          
        ]
      } 
    }
  ]
}
    
    
