<script src="https://code.jquery.com/jquery-3.1.1.min.js"></script>
<script src="https://code.highcharts.com/highcharts.js"></script>
<script src="https://code.highcharts.com/highcharts-more.js"></script>
<script src="https://code.highcharts.com/modules/heatmap.js"></script>
<script src="https://code.highcharts.com/modules/sunburst.js"></script>
<script src="https://code.highcharts.com/modules/streamgraph.js"></script>
<script src="https://code.highcharts.com/modules/variable-pie.js"></script>
<script src="https://code.highcharts.com/modules/series-label.js"></script>
<script src="https://code.highcharts.com/modules/annotations.js"></script>
<script src="https://code.highcharts.com/modules/exporting.js"></script>
<script src="https://code.highcharts.com/modules/export-data.js"></script>
<script src="https://code.highcharts.com/modules/accessibility.js"></script>
<script src="https://code.highcharts.com/maps/highmaps.js"></script>
<script src="https://code.highcharts.com/maps/modules/data.js"></script>
<script src="https://code.highcharts.com/maps/modules/exporting.js"></script>
<script src="https://code.highcharts.com/maps/modules/offline-exporting.js"></script>
<script src="http://code.highcharts.com/maps/modules/map.js"></script>
<script src="https://code.highcharts.com/mapdata/custom/world.js"></script>

<head>
<style>
  .button {
    background-color: #34495E;
    border: none;
    border-radius: 2px;
    color: white;
    margin: 2px 2px;
    padding: 8px 8px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 12px;
  }

  #sunburst{
    maxWidth: 150%;
  }


</style>
</head>


<body>

# Abstract TO DO


## Food balance

<figure class="highcharts-figure">
  <div id="evolution_by_years"></div>
  <button class="button" id="consumption">Food Consumption</button>
  <button class="button" id="import_">Import Quantity</button>
  <button class="button" id="production">Production</button>
</figure>

<figure class="highcharts-figure">
  <div id="pct_change_by_years"></div>
  <button class="button" id="consumption_pct">Food Consumption</button>
  <button class="button" id="import_pct">Import Quantity</button>
  <button class="button" id="production_pct">Production</button>
</figure>

<figure class="highcharts-figure">
  <div id="imp_exp_prod"></div>
</figure>

<h2>Food Importation</h2>
<p>We looked into the kind of food we are used to eat and how much of it actually comes from Switzerland. However, it still remains unknown at this point where the rest of our food comes from.
Since we already analyzed the evolution of our importations throughout the years, it is interesting here to focus on other dimensions such as the provenance of our importations as well as their proportion.
For this reason we only study here the most recent data to obtain results that relate to us as much as possible.</p>
<figure class="highcharts-figure">
  <div id="import_map"></div>
  <button class="button" id="overview">Overview</button>
  <button class="button" id="alcohol">Alcohol</button>
  <button class="button" id="cereals">Cereals</button>
  <button class="button" id="fruits">Fruits</button>
  <button class="button" id="meat">Meat</button>
  <button class="button" id="dairy">Dairy</button>
  <button class="button" id="starchy">Potatoes</button>
  <button class="button" id="sugar">Sugar</button>
  <button class="button" id="vegetables">Vegetables</button>
</figure>

<figure class="highcharts-figure">
  <div id="sunburst"></div>

</figure>

## Impact on Prices

<figure class="highcharts-figure">
  <div id="prod_price_maize"></div>
  <p class="highcharts-description">
  </p>
</figure>

<figure class="highcharts-figure">
  <div id="maize_price_evo"></div>
</figure>

## Impact on environment

<figure class="highcharts-figure">
  <div id="co2_loss"></div>
</figure>

<figure class="highcharts-figure">
  <div id="footprint"></div>
</figure>
</body>


<script>
  var chart = Highcharts.chart('evolution_by_years', {
    chart: {
      type: 'area'
    },
    title: {
      text: 'Food Consumption'
    },

    xAxis: {
      categories: [1961, 1962, 1963, 1964, 1965, 1966, 1967, 1968, 1969, 1970, 1971,
        1972, 1973, 1974, 1975, 1976, 1977, 1978, 1979, 1980, 1981, 1982,
        1983, 1984, 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993,
        1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2002, 2003, 2004,
        2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013
      ],
      tickmarkPlacement: 'on',
      title: {
        enabled: false
      }
    },
    yAxis: {
      title: {
        text: 'Quantity (kg/capita/year)'
      }
    },
    tooltip: {
      split: true,
      valueSuffix: 'kg'
    },
    plotOptions: {
      area: {
        stacking: 'normal',
        lineColor: '#666666',
        lineWidth: 1,
        marker: {
          enabled: false
        }
      }
    },

    series: [{
      name: 'Alcoholic Beverages',
      data: [122.53, 130.84, 129.59, 132.09, 124.89, 126.33, 131.7, 128.75,
        133.22, 126.18, 131.86, 127.37, 131.38, 127.84, 128.72, 125.,
        119.86, 119.21, 120.8, 124.93, 130.25, 137.2, 136.73, 129.14,
        126.09, 124.11, 123.44, 119.05, 123.09, 120.48, 122., 120.34,
        112.01, 110.14, 103.6, 102.65, 101.18, 98.62, 98.84, 95.94,
        107.1, 104.27, 104.61, 100.09, 99.06, 99.89, 101.05, 101.52,
        99.89, 100.24, 99.56, 98., 97.75
      ]
    }, {
      name: 'Cereals - Excluding Beer',
      data: [138.88, 117.4, 124.84, 118.99, 123.89, 115.14, 107.57, 109.9,
        109.33, 109.1, 105.45, 110.7, 106.23, 97.04, 92.88, 96.42,
        103.11, 106.2, 99.67, 104.45, 105.63, 98.2, 94.28, 93.,
        96.1, 95.26, 99.82, 98.48, 100.51, 106.33, 104.73, 110.06,
        104.5, 105.61, 105.26, 106.69, 108.66, 111.06, 111.31, 116.99,
        106.78, 109.82, 109.8, 107.75, 105.31, 105.76, 106.04, 100.3,
        107.08, 102.94, 108.75, 99.81, 98.68
      ]
    }, {
      name: 'Fruits - Excluding Wine',
      data: [138.26, 170.61, 142.92, 144.94, 160.23, 153.86, 212.07, 144.1,
        191.42, 143.29, 150.82, 118.05, 148.6, 129.61, 148.29, 129.45,
        132., 139.43, 153.94, 144.07, 125.21, 146.63, 128.47, 131.09,
        126.06, 130.64, 125.55, 135.03, 129.21, 127.8, 117.24, 124.5,
        119.28, 116.33, 115.99, 121.44, 112.16, 116.41, 95.06, 89.81,
        87.85, 87.6, 80.18, 76.36, 71.93, 74.3, 79.42, 86.5,
        95.74, 103.02, 105.38, 109.3, 103.61
      ]
    }, {
      name: 'Meat',
      data: [56.91, 60.2, 59.48, 62.65, 62.03, 62.98, 64.86, 66.71, 68.79,
        71.26, 72.96, 74.14, 76.72, 74.44, 71.52, 75.8, 78.49, 79.47,
        82.2, 85.36, 84.4, 86.02, 84.79, 85.1, 86.37, 86.56, 86.01,
        85.06, 84.79, 83.16, 83.36, 80.7, 78.09, 74.52, 74.81, 73.15,
        72.02, 73.6, 72.72, 71.55, 72.3, 72.81, 72.37, 72.33, 72.41,
        72.21, 73.18, 74.61, 73.51, 75.02, 74.74, 72.04, 72.32
      ]
    }, {
      name: 'Milk - Excluding Butter',
      data: [314.71, 307.12, 303.06, 303.14, 309.87, 302.42, 282.18, 281.66,
        282.07, 297.18, 284.86, 282.16, 293.96, 295.67, 307.26, 318.27,
        338.35, 340.24, 321.38, 329.32, 332.99, 334.63, 334.55, 346.9,
        342.13, 334.35, 334.78, 322.76, 329.9, 339.77, 347.02, 339.62,
        338.13, 335.51, 325.53, 321.93, 319.24, 313.95, 284.5, 318.78,
        301.44, 310.55, 314.35, 309.32, 307.2, 313.7, 315.81, 308.75,
        314.45, 314.05, 316.22, 313.93, 318.69
      ]
    }, {
      name: 'Starchy Roots',
      data: [68.46, 68.47, 68.86, 64.38, 59.58, 58.18, 57.61, 56.22, 56.12,
        55.14, 54.88, 52.22, 51.43, 49.52, 49.19, 48.86, 52.7, 49.63,
        49.81, 48.58, 47.83, 50.26, 46.36, 50.4, 47.56, 49.63, 46.64,
        46.23, 45.12, 45.86, 45.3, 48.13, 46.42, 49.4, 48.05, 48.31,
        44.37, 43.49, 44.92, 58.83, 45.44, 44.82, 44.68, 42.16, 40.77,
        37.28, 39.11, 43.26, 44.06, 43.61, 41.94, 44.3, 41.02
      ]
    }, {
      name: 'Sugar & Sweeteners',
      data: [53.46, 54.6, 44.57, 50.82, 50.43, 50.22, 48.72, 53.56, 52.16,
        53.32, 51.78, 56.88, 50.66, 53.8, 37.08, 43.11, 52.26, 44.81,
        45.8, 46.31, 48.29, 45.13, 50.82, 48.11, 46.82, 49.17, 48.26,
        52.34, 50.1, 51., 44.92, 48.85, 50.11, 45.17, 48.67, 52.44,
        51.54, 48.37, 50.38, 54.45, 53.78, 57.15, 56.86, 59.42, 58.85,
        59.95, 58.95, 59.43, 58.12, 58.72, 58.22, 60.35, 60.41
      ]
    }, {
      name: 'Vegetables',
      data: [73.87, 70.08, 77.35, 74.78, 73.02, 78.52, 77.51, 76.32,
        78.38, 76.74, 78.55, 80.91, 83.92, 87.33, 77.44, 85.2,
        84.69, 96.14, 83.37, 94.33, 99.79, 95.68, 93.41, 98.37,
        96.35, 88.76, 87.82, 94.76, 91.01, 90.69, 93.77, 91.93,
        90.07, 92.31, 96.34, 96.84, 94.62, 96.29, 94.88, 100.32,
        97.47, 98.88, 95.08, 95.93, 87.99, 88.27, 90.45, 95.38,
        99.82, 103.99, 113.42, 108.25, 108.7
      ]
    }],
    plotOptions: {
      area: {
        stacking: 'normal',
        lineColor: '#666666',
        lineWidth: 1,
        marker: {
          enabled: false
        }
      }
    }

  });


  $('#consumption').click(function() {
    chart.update({
      title: {
        text: 'Food Consumption'
      },
      tooltip: {
        split: true,
        valueSuffix: 'kg'
      },
      series: [{
        name: 'Alcoholic Beverages',
        data: [122.53, 130.84, 129.59, 132.09, 124.89, 126.33, 131.7, 128.75,
          133.22, 126.18, 131.86, 127.37, 131.38, 127.84, 128.72, 125.,
          119.86, 119.21, 120.8, 124.93, 130.25, 137.2, 136.73, 129.14,
          126.09, 124.11, 123.44, 119.05, 123.09, 120.48, 122., 120.34,
          112.01, 110.14, 103.6, 102.65, 101.18, 98.62, 98.84, 95.94,
          107.1, 104.27, 104.61, 100.09, 99.06, 99.89, 101.05, 101.52,
          99.89, 100.24, 99.56, 98., 97.75
        ]
      }, {
        name: 'Cereals - Excluding Beer',
        data: [138.88, 117.4, 124.84, 118.99, 123.89, 115.14, 107.57, 109.9,
          109.33, 109.1, 105.45, 110.7, 106.23, 97.04, 92.88, 96.42,
          103.11, 106.2, 99.67, 104.45, 105.63, 98.2, 94.28, 93.,
          96.1, 95.26, 99.82, 98.48, 100.51, 106.33, 104.73, 110.06,
          104.5, 105.61, 105.26, 106.69, 108.66, 111.06, 111.31, 116.99,
          106.78, 109.82, 109.8, 107.75, 105.31, 105.76, 106.04, 100.3,
          107.08, 102.94, 108.75, 99.81, 98.68
        ]
      }, {
        name: 'Fruits - Excluding Wine',
        data: [138.26, 170.61, 142.92, 144.94, 160.23, 153.86, 212.07, 144.1,
          191.42, 143.29, 150.82, 118.05, 148.6, 129.61, 148.29, 129.45,
          132., 139.43, 153.94, 144.07, 125.21, 146.63, 128.47, 131.09,
          126.06, 130.64, 125.55, 135.03, 129.21, 127.8, 117.24, 124.5,
          119.28, 116.33, 115.99, 121.44, 112.16, 116.41, 95.06, 89.81,
          87.85, 87.6, 80.18, 76.36, 71.93, 74.3, 79.42, 86.5,
          95.74, 103.02, 105.38, 109.3, 103.61
        ]
      }, {
        name: 'Meat',
        data: [56.91, 60.2, 59.48, 62.65, 62.03, 62.98, 64.86, 66.71, 68.79,
          71.26, 72.96, 74.14, 76.72, 74.44, 71.52, 75.8, 78.49, 79.47,
          82.2, 85.36, 84.4, 86.02, 84.79, 85.1, 86.37, 86.56, 86.01,
          85.06, 84.79, 83.16, 83.36, 80.7, 78.09, 74.52, 74.81, 73.15,
          72.02, 73.6, 72.72, 71.55, 72.3, 72.81, 72.37, 72.33, 72.41,
          72.21, 73.18, 74.61, 73.51, 75.02, 74.74, 72.04, 72.32
        ]
      }, {
        name: 'Milk - Excluding Butter',
        data: [314.71, 307.12, 303.06, 303.14, 309.87, 302.42, 282.18, 281.66,
          282.07, 297.18, 284.86, 282.16, 293.96, 295.67, 307.26, 318.27,
          338.35, 340.24, 321.38, 329.32, 332.99, 334.63, 334.55, 346.9,
          342.13, 334.35, 334.78, 322.76, 329.9, 339.77, 347.02, 339.62,
          338.13, 335.51, 325.53, 321.93, 319.24, 313.95, 284.5, 318.78,
          301.44, 310.55, 314.35, 309.32, 307.2, 313.7, 315.81, 308.75,
          314.45, 314.05, 316.22, 313.93, 318.69
        ]
      }, {
        name: 'Starchy Roots',
        data: [68.46, 68.47, 68.86, 64.38, 59.58, 58.18, 57.61, 56.22, 56.12,
          55.14, 54.88, 52.22, 51.43, 49.52, 49.19, 48.86, 52.7, 49.63,
          49.81, 48.58, 47.83, 50.26, 46.36, 50.4, 47.56, 49.63, 46.64,
          46.23, 45.12, 45.86, 45.3, 48.13, 46.42, 49.4, 48.05, 48.31,
          44.37, 43.49, 44.92, 58.83, 45.44, 44.82, 44.68, 42.16, 40.77,
          37.28, 39.11, 43.26, 44.06, 43.61, 41.94, 44.3, 41.02
        ]
      }, {
        name: 'Sugar & Sweeteners',
        data: [53.46, 54.6, 44.57, 50.82, 50.43, 50.22, 48.72, 53.56, 52.16,
          53.32, 51.78, 56.88, 50.66, 53.8, 37.08, 43.11, 52.26, 44.81,
          45.8, 46.31, 48.29, 45.13, 50.82, 48.11, 46.82, 49.17, 48.26,
          52.34, 50.1, 51., 44.92, 48.85, 50.11, 45.17, 48.67, 52.44,
          51.54, 48.37, 50.38, 54.45, 53.78, 57.15, 56.86, 59.42, 58.85,
          59.95, 58.95, 59.43, 58.12, 58.72, 58.22, 60.35, 60.41
        ]
      }, {
        name: 'Vegetables',
        data: [73.87, 70.08, 77.35, 74.78, 73.02, 78.52, 77.51, 76.32,
          78.38, 76.74, 78.55, 80.91, 83.92, 87.33, 77.44, 85.2,
          84.69, 96.14, 83.37, 94.33, 99.79, 95.68, 93.41, 98.37,
          96.35, 88.76, 87.82, 94.76, 91.01, 90.69, 93.77, 91.93,
          90.07, 92.31, 96.34, 96.84, 94.62, 96.29, 94.88, 100.32,
          97.47, 98.88, 95.08, 95.93, 87.99, 88.27, 90.45, 95.38,
          99.82, 103.99, 113.42, 108.25, 108.7
        ]
      }]
    });
  });

  $('#import_').click(function() {
    chart.update({
      title: {
        text: 'Import Quantity'
      },
      yAxis: {
        title: {
          text: 'Import Quantity (1000 tonnes/year)'
        }
      },
      tooltip: {
        split: true,
        valueSuffix: ' tonnes'
      },
      series: [{
        name: 'Alcoholic Beverages',
        data: [143., 157., 174., 174., 188., 185., 191., 197., 223., 226., 243.,
          252., 291., 284., 265., 253., 253., 265., 260., 288., 330., 334.,
          289., 294., 304., 284., 295., 268., 282., 266., 278., 265., 272.,
          275., 277., 280., 282., 291., 295., 280., 305., 305., 308., 301.,
          309., 326., 333., 336., 348., 366., 370., 378., 378.
        ]
      }, {
        name: 'Cereals - Excluding Beer',
        data: [997., 1129., 1102., 1129., 1228., 1381., 1448., 1252., 1465.,
          1573., 1508., 1469., 1661., 1613., 1658., 1621., 1367., 1548.,
          1373., 1416., 1377., 1364., 1422., 1245., 1186., 1180., 1108.,
          1013., 848., 651., 741., 685., 713., 597., 724., 623.,
          638., 625., 646., 804., 714., 841., 941., 865., 734.,
          853., 1110., 1100., 1017., 1084., 1268., 1093., 1173.
        ]
      }, {
        name: 'Fruits - Excluding Wine',
        data: [313., 331., 321., 361., 421., 400., 442., 409., 458., 454., 460.,
          489., 492., 483., 450., 432., 449., 456., 477., 490., 467., 491.,
          489., 472., 451., 470., 507., 535., 526., 544., 580., 576., 560.,
          602., 585., 578., 573., 584., 611., 626., 629., 645., 658., 677.,
          693., 707., 688., 725., 723., 710., 701., 696., 746.
        ]
      }, {
        name: 'Meat',
        data: [50., 69., 68., 86., 71., 76., 81., 69., 80., 88., 86.,
          90., 95., 65., 54., 59., 58., 66., 64., 64., 72., 65.,
          68., 72., 71., 74., 81., 88., 85., 83., 80., 77., 78.,
          85., 80., 94., 95., 92., 93., 103., 91., 92., 97., 99.,
          99., 103., 112., 135., 119., 122., 123., 115., 126.
        ]
      }, {
        name: 'Milk - Excluding Butter',
        data: [172., 218., 225., 327., 437., 357., 460., 281., 302., 425., 452.,
          404., 328., 333., 322., 316., 310., 308., 311., 320., 313., 313.,
          317., 327., 326., 335., 361., 338., 341., 357., 375., 380., 391.,
          385., 388., 391., 412., 371., 352., 348., 283., 286., 297., 296.,
          299., 320., 370., 417., 434., 446., 457., 489., 507.
        ]
      }, {
        name: 'Starchy Roots',
        data: [48., 49., 34., 33., 31., 25., 26., 12., 106., 106., 88.,
          90., 126., 115., 74., 115., 335., 176., 119., 157., 134., 168.,
          178., 168., 164., 187., 219., 167., 213., 194., 205., 176., 215.,
          241., 236., 194., 226., 221., 278., 247., 196., 189., 166., 123.,
          152., 208., 131., 205., 177., 146., 124., 94., 150.
        ]
      }, {
        name: 'Sugar & Sweeteners',
        data: [277., 258., 226., 228., 280., 255., 273., 302., 219., 259., 283.,
          272., 254., 275., 170., 256., 286., 210., 197., 180., 209., 233.,
          213., 214., 221., 220., 205., 212., 185., 177., 190., 220., 225.,
          227., 232., 237., 211., 207., 235., 296., 285., 330., 361., 413.,
          447., 434., 466., 395., 310., 230., 270., 248., 325.
        ]
      }, {
        name: 'Vegetables',
        data: [157., 178., 185., 183., 213., 222., 229., 234., 248., 273., 257.,
          290., 314., 323., 266., 319., 286., 327., 312., 343., 346., 332.,
          341., 344., 334., 361., 377., 357., 345., 348., 363., 367., 359.,
          406., 422., 400., 397., 413., 423., 442., 439., 453., 452., 458.,
          432., 473., 460., 492., 475., 493., 476., 474., 505.
        ]
      }]
    });
  });

  $('#production').click(function() {
    chart.update({

      title: {
        text: 'Production'
      },
      yAxis: {
        title: {
          text: 'Production Quantity (1000 tonnes/year)'
        }
      },
      tooltip: {
        split: true,
        valueSuffix: ' tonnes'
      },
      series: [{
        name: 'Alcoholic Beverages',
        data: [529., 578., 589., 620., 576., 566., 623., 606., 617., 620., 595.,
          573., 635., 573., 595., 599., 561., 509., 550., 529., 543., 637.,
          621., 560., 564., 574., 562., 549., 608., 572., 573., 568., 515.,
          520., 495., 476., 445., 449., 456., 438., 499., 481., 491., 489.,
          458., 467., 472., 487., 483., 473., 483., 469., 437.
        ]
      }, {
        name: 'Cereals - Excluding Beer',
        data: [518., 697., 515., 632., 558., 567., 673., 653., 640.,
          634., 743., 738., 750., 857., 757., 796., 690., 835.,
          875., 789., 864., 929., 900., 1118., 1054., 960., 939.,
          1244., 1411., 1268., 1313., 1213., 1292., 1249., 1281., 1348.,
          1223., 1263., 1055., 1206., 1094., 1101., 847., 1089., 1057.,
          1013., 1011., 1001., 1006., 924., 972., 922., 838.
        ]
      }, {
        name: 'Fruits - Excluding Wine',
        data: [720., 908., 740., 797., 586., 777., 1087., 756., 963.,
          759., 768., 608., 846., 552., 879., 666., 644., 671.,
          920., 683., 569., 1087., 713., 771., 664., 832., 546.,
          909., 704., 720., 477., 846., 598., 581., 533., 670.,
          469., 796., 518., 708., 466., 513., 460., 551., 439.,
          485., 533., 508., 506., 408., 582., 443., 398.
        ]
      }, {
        name: 'Meat',
        data: [260., 265., 268., 276., 294., 299., 312., 341., 349., 358., 372.,
          379., 396., 413., 405., 426., 443., 439., 457., 480., 465., 483.,
          477., 477., 492., 494., 488., 474., 478., 477., 484., 477., 463.,
          436., 448., 430., 421., 434., 429., 412., 432., 440., 433., 435.,
          441., 441., 445., 440., 454., 471., 476., 473., 468.
        ]
      }, {
        name: 'Milk - Excluding Butter',
        data: [3094., 3140., 3117., 3038., 3117., 3153., 3274., 3322., 3214.,
          3204., 3160., 3234., 3295., 3360., 3396., 3473., 3511., 3542.,
          3671., 3679., 3680., 3687., 3755., 3875., 3867., 3867., 3783.,
          3797., 3911., 3885., 3936., 3890., 3979., 3903., 3929., 3878.,
          3877., 3905., 3874., 3907., 3962., 3964., 3906., 3936., 3957.,
          3958., 3936., 4097., 4094., 4106., 4144., 4112., 4032.
        ]
      }, {
        name: 'Starchy Roots',
        data: [1239., 1127., 1246., 1206., 906., 1049., 1125., 1098., 979.,
          977., 1093., 824., 910., 929., 908., 769., 713., 893.,
          871., 853., 1048., 960., 711., 923., 817., 743., 658.,
          836., 770., 712., 711., 841., 859., 634., 631., 812.,
          687., 560., 484., 601., 518., 526., 458., 527., 485.,
          391., 491., 473., 522., 421., 515., 447., 360.
        ]
      }, {
        name: 'Sugar & Sweeteners',
        data: [36., 30., 46., 61., 46., 60., 65., 73., 62., 63., 76.,
          68., 79., 77., 61., 84., 80., 109., 119., 108., 136., 123.,
          126., 134., 141., 132., 126., 152., 157., 162., 140., 140., 157.,
          130., 147., 204., 201., 195., 180., 241., 182., 225., 189., 223.,
          250., 207., 284., 284., 317., 290., 358., 317., 279.
        ]
      }, {
        name: 'Vegetables',
        data: [299., 248., 286., 269., 238., 288., 280., 260., 260., 257., 291.,
          261., 273., 265., 258., 261., 289., 330., 259., 298., 362., 335.,
          328., 377., 361., 262., 246., 314., 308., 308., 308., 307., 307.,
          286., 301., 322., 312., 308., 288., 310., 296., 312., 296., 329.,
          313., 290., 314., 326., 381., 364., 466., 435., 417.
        ]
      }]
    });
  });

  Highcharts.chart('imp_exp_prod', {
    chart: {
      type: 'area'
    },
    title: {
      text: 'Proportion of import, export and production in 2013'
    },
    xAxis: {
      categories: ['Cereals - Excluding Beer', 'Starchy Roots', 'Sugar & Sweeteners',
        'Vegetables', 'Fruits - Excluding Wine', 'Alcoholic Beverages',
        'Meat', 'Milk - Excluding Butter'
      ],
      tickmarkPlacement: 'on',
      title: {
        enabled: false
      }
    },
    yAxis: {
      labels: {
        format: '{value}%'
      },
      title: {
        enabled: false
      }
    },
    tooltip: {
      pointFormat: '<span style="color:{series.color}">{series.name}</span>: <b>{point.percentage:.1f}%</b> ({point.y:,.0f} 000 tonnes)<br/>',
      split: true
    },
    plotOptions: {
      area: {
        stacking: 'percent',
        lineColor: '#ffffff',
        lineWidth: 1,
        marker: {
          lineWidth: 1,
          lineColor: '#ffffff'
        },
        accessibility: {
          pointDescriptionFormatter: function(point) {
            function round(x) {
              return Math.round(x * 100) / 100;
            }
            return (point.index + 1) + ', ' + point.category + ', ' +
              point.y + ' , ' + round(point.percentage) + '%, ' +
              point.series.name;
          }
        }
      }
    },
    series: [{
      name: 'Import Quantity',
      data: [1173., 150., 325., 505., 746., 378., 126., 507.]
    }, {
      name: 'Production Quantity',
      data: [838., 360., 279., 417., 398., 437., 468., 4032.]
    }, {
      name: 'Export Quantity',
      data: [61., 5., 180., 15., 139., 9., 10., 580.]
    }]
  });


  function getPointCategoryName(point, dimension) {
    var series = point.series,
      isY = dimension === 'y',
      axis = series[isY ? 'yAxis' : 'xAxis'];
    return axis.categories[point[isY ? 'y' : 'x']];
  }

  function getPointCategoryName(point, dimension) {
    var series = point.series,
      isY = dimension === 'y',
      axis = series[isY ? 'yAxis' : 'xAxis'];
    return axis.categories[point[isY ? 'y' : 'x']];
  }

  var chart_pct = Highcharts.chart('pct_change_by_years', {
    chart: {
      type: 'heatmap'
    },

    title: {
      text: 'Percentage change in food consumption every 10 years'
    },

    xAxis: {
      categories: [1963, 1973, 1983, 1993, 2003, 2013]
    },

    yAxis: {
      categories: ['Cereals - Excluding Beer', 'Starchy Roots', 'Sugar & Sweeteners',
        'Vegetables', 'Fruits - Excluding Wine', 'Alcoholic Beverages', 'Meat',
        'Milk - Excluding Butter'
      ],
      title: 'Element group'

    },

    accessibility: {
      point: {
        descriptionFormatter: function(point) {
          var ix = point.index + 1,
            xName = getPointCategoryName(point, 'x'),
            yName = getPointCategoryName(point, 'y'),
            val = point.value;
          return ix + '. ' + xName + ' sales ' + yName + ', ' + val + '.';
        }
      }
    },

    colorAxis: {
      min: -30,
      stops: [
        [0, '#3060cf'],
        [0.5, '#ffffff'],
        [0.9, '#c4463a']
      ]
    },

    legend: {
      align: 'right',
      layout: 'vertical',
      margin: 0,
      verticalAlign: 'top',
      y: 50,
      symbolHeight: 282
    },

    tooltip: {
      formatter: function() {
        return getPointCategoryName(this.point, 'y') + ': Change of ' + this.point.value + '% from ' + (getPointCategoryName(this.point, 'x') - 10) + ' to ' + getPointCategoryName(this.point, 'x');
      }
    },

    series: [{
      name: 'Percentage change',
      borderWidth: 1,
      data: [
        [0, 0, -14.9],
        [1, 0, -11.2],
        [2, 0, 10.8],
        [3, 0, 5.1],
        [4, 0, -10.1],
        [0, 1, -25.3],
        [1, 1, -9.9],
        [2, 1, 0.1],
        [3, 1, -3.7],
        [4, 1, -8.2],
        [0, 2, 13.7],
        [1, 2, 0.3],
        [2, 2, -1.4],
        [3, 2, 13.5],
        [4, 2, 6.2],
        [0, 3, 8.5],
        [1, 3, 11.3],
        [2, 3, -3.6],
        [3, 3, 5.6],
        [4, 3, 14.3],
        [0, 4, 4.0],
        [1, 4, -13.5],
        [2, 4, -7.2],
        [3, 4, -32.8],
        [4, 4, 29.2],
        [0, 5, 1.4],
        [1, 5, 4.1],
        [2, 5, -18.1],
        [3, 5, -6.6],
        [4, 5, -6.6],
        [0, 6, 29.0],
        [1, 6, 10.5],
        [2, 6, -7.9],
        [3, 6, -7.3],
        [4, 6, -0.1],
        [0, 7, -3.0],
        [1, 7, 13.8],
        [2, 7, 1.1],
        [3, 7, -7.0],
        [4, 7, 1.4]
      ],
      dataLabels: {
        enabled: false,
        color: '#000000'
      }
    }],

    responsive: {
      rules: [{
        condition: {
          maxWidth: 500
        },
        chartOptions: {
          yAxis: {
            labels: {
              formatter: function() {
                return this.value.charAt(0);
              }
            }
          }
        }
      }]
    }

  });
  $('#consumption_pct').click(function() {
    chart_pct.update({

      title: {
        text: 'Percentage change in food consumption every 10 years'
      },
      colorAxis: {
        min: -30,
        stops: [
          [0, '#3060cf'],
          [0.5, '#ffffff'],
          [0.9, '#c4463a']
        ]
      },

      series: [{
          name: 'Percentage change',
          borderWidth: 1,
          data: [
            [0, 0, -14.9],
            [1, 0, -11.2],
            [2, 0, 10.8],
            [3, 0, 5.1],
            [4, 0, -10.1],
            [0, 1, -25.3],
            [1, 1, -9.9],
            [2, 1, 0.1],
            [3, 1, -3.7],
            [4, 1, -8.2],
            [0, 2, 13.7],
            [1, 2, 0.3],
            [2, 2, -1.4],
            [3, 2, 13.5],
            [4, 2, 6.2],
            [0, 3, 8.5],
            [1, 3, 11.3],
            [2, 3, -3.6],
            [3, 3, 5.6],
            [4, 3, 14.3],
            [0, 4, 4.0],
            [1, 4, -13.5],
            [2, 4, -7.2],
            [3, 4, -32.8],
            [4, 4, 29.2],
            [0, 5, 1.4],
            [1, 5, 4.1],
            [2, 5, -18.1],
            [3, 5, -6.6],
            [4, 5, -6.6],
            [0, 6, 29.0],
            [1, 6, 10.5],
            [2, 6, -7.9],
            [3, 6, -7.3],
            [4, 6, -0.1],
            [0, 7, -3.0],
            [1, 7, 13.8],
            [2, 7, 1.1],
            [3, 7, -7.0],
            [4, 7, 1.4]
          ],
          dataLabels: {
            enabled: false,
            color: '#000000'
          }
        }

      ]
    });
  });
  $('#import_pct').click(function() {
    chart_pct.update({

      title: {
        text: 'Percentage change in import quantity every 10 years'
      },
      colorAxis: {
        min: -30,
        max: 30,
        stops: [
          [0, '#3060cf'],
          [0.5, '#ffffff'],
          [0.9, '#c4463a']
        ]
      },

      series: [{
          name: 'Percentage change',
          borderWidth: 1,
          data: [
            [0, 0, 50.7],
            [1, 0, -14.4],
            [2, 0, -49.9],
            [3, 0, 32.0],
            [4, 0, 24.7],
            [0, 1, 270.6],
            [1, 1, 41.3],
            [2, 1, 20.8],
            [3, 1, -22.8],
            [4, 1, -9.6],
            [0, 2, 12.4],
            [1, 2, -16.1],
            [2, 2, 5.6],
            [3, 2, 60.4],
            [4, 2, -10.0],
            [0, 3, 69.7],
            [1, 3, 8.6],
            [2, 3, 5.3],
            [3, 3, 25.9],
            [4, 3, 11.7],
            [0, 4, 53.3],
            [1, 4, -0.6],
            [2, 4, 14.5],
            [3, 4, 17.5],
            [4, 4, 13.4],
            [0, 5, 67.2],
            [1, 5, -0.7],
            [2, 5, -5.9],
            [3, 5, 13.2],
            [4, 5, 22.7],
            [0, 6, 39.7],
            [1, 6, -28.4],
            [2, 6, 14.7],
            [3, 6, 24.4],
            [4, 6, 29.9],
            [0, 7, 45.8],
            [1, 7, -3.4],
            [2, 7, 23.3],
            [3, 7, -24.0],
            [4, 7, 70.7]
          ],
          dataLabels: {
            enabled: false,
            color: '#000000'
          }
        }

      ]
    });
  });
  $('#production_pct').click(function() {
    chart_pct.update({

      title: {
        text: 'Percentage change in production quantity every 10 years'
      },
      colorAxis: {
        min: -30,
        max: 30,
        stops: [
          [0, '#3060cf'],
          [0.5, '#ffffff'],
          [0.9, '#c4463a']
        ]
      },

      series: [{
          name: 'Percentage change',
          borderWidth: 1,
          data: [
            [0, 0, 45.6],
            [1, 0, 20.0],
            [2, 0, 43.6],
            [3, 0, -34.4],
            [4, 0, -1.1],
            [0, 1, -27.0],
            [1, 1, -21.9],
            [2, 1, 20.8],
            [3, 1, -46.7],
            [4, 1, -21.4],
            [0, 2, 71.7],
            [1, 2, 59.5],
            [2, 2, 24.6],
            [3, 2, 20.4],
            [4, 2, 47.6],
            [0, 3, -4.5],
            [1, 3, 20.1],
            [2, 3, -6.4],
            [3, 3, -3.6],
            [4, 3, 40.9],
            [0, 4, 14.3],
            [1, 4, -15.7],
            [2, 4, -16.1],
            [3, 4, -23.1],
            [4, 4, -13.5],
            [0, 5, 7.8],
            [1, 5, -2.2],
            [2, 5, -17.1],
            [3, 5, -4.7],
            [4, 5, -11.0],
            [0, 6, 47.8],
            [1, 6, 20.5],
            [2, 6, -2.9],
            [3, 6, -6.5],
            [4, 6, 8.1],
            [0, 7, 5.7],
            [1, 7, 14.0],
            [2, 7, 6.0],
            [3, 7, -1.8],
            [4, 7, 3.2]
          ],
          dataLabels: {
            enabled: false,
            color: '#000000'
          }
        }

      ]
    });
  });

  var overview = [
  {
    name: "France",
    value: 4.0
  }, {
    name: "Spain",
    value: 7.0
  }, {
    name: "Netherlands",
    value: 5.0
  }, {
    name: "Germany",
    value: 1.0
  }, {
    name: "Italy",
    value: 7.0
  }, {
    name: "Brazil",
    value: 3.0
  }, {
    name: "Austria",
    value: 6.0
  }, {
    name: "Portugal",
    value: 0.0
  }, {
    name: "Czechia",
    value: 6.0
  }, {
    name: "Israel",
    value: 5.0
  }, {
    name: "Hungary",
    value: 3.0
  }, {
    name: "Colombia",
    value: 2.0
  }, {
    name: "Egypt",
    value: 5.0
  }, {
    name: "Canada",
    value: 1.0
  }, {
    name: "Slovakia",
    value: 1.0
  }, {
    name: "Belgium",
    value: 5.0
  }, {
    name: "Ireland",
    value: 3.0
  }, {
    name: "Morocco",
    value: 7.0
  }, {
    name: "Costa Rica",
    value: 2.0
  }, {
    name: "South Africa",
    value: 2.0
  }, {
    name: "Australia",
    value: 3.0
  }, {
    name: "Peru",
    value: 2.0
  }, {
    name: "Panama",
    value: 2.0
  }, {
    name: "Turkey",
    value: 7.0
  }, {
    name: "New Zealand",
    value: 3.0
  }];
  var cereals = [
  {
    name: "Germany",
    value: 372343.0
  }, {
    name: "France",
    value: 269415.0
  }, {
    name: "Italy",
    value: 98419.0
  }, {
    name: "Austria",
    value: 92490.0
  }, {
    name: "Hungary",
    value: 78851.0
  }, {
    name: "Canada",
    value: 60715.0
  }, {
    name: "Slovakia",
    value: 55322.0
  }, {
    name: "Brazil",
    value: 48743.0
  }, {
    name: "Czechia",
    value: 37508.0
  }, {
    name: "China, mainland",
    value: 34360.0
  }, {
    name: "Romania",
    value: 25220.0
  }, {
    name: "Finland",
    value: 20952.0
  }, {
    name: "Thailand",
    value: 16215.0
  }, {
    name: "Argentina",
    value: 13693.0
  }, {
    name: "Belgium",
    value: 12169.0
  }, {
    name: "India",
    value: 8338.0
  }, {
    name: "Netherlands",
    value: 7772.0
  }, {
    name: "Ukraine",
    value: 7472.0
  }, {
    name: "Spain",
    value: 7021.0
  }, {
    name: "Russian Federation",
    value: 6885.0
  }, {
    name: "United States of America",
    value: 6228.0
  }, {
    name: "United Kingdom",
    value: 4501.0
  }, {
    name: "Uruguay",
    value: 4154.0
  }, {
    name: "Sweden",
    value: 3600.0
  }, {
    name: "Poland",
    value: 3486.0
  }, {
    name: "Turkey",
    value: 2584.0
  }, {
    name: "Serbia",
    value: 2421.0
  }, {
    name: "Paraguay",
    value: 2359.0
  }, {
    name: "Portugal",
    value: 2060.0
  }, {
    name: "Pakistan",
    value: 1921.0
  }, {
    name: "Slovenia",
    value: 1542.0
  }, {
    name: "Myanmar",
    value: 1065.0
  }, {
    name: "Denmark",
    value: 886.0
  }, {
    name: "Viet Nam",
    value: 812.0
  }, {
    name: "Bulgaria",
    value: 792.0
  }, {
    name: "Bolivia (Plurinational State of)",
    value: 718.0
  }, {
    name: "Ireland",
    value: 561.0
  }, {
    name: "Kazakhstan",
    value: 519.0
  }, {
    name: "Greece",
    value: 441.0
  }, {
    name: "Singapore",
    value: 341.0
  }, {
    name: "Republic of Korea",
    value: 281.0
  }, {
    name: "Japan",
    value: 278.0
  }, {
    name: "Sri Lanka",
    value: 259.0
  }, {
    name: "Lithuania",
    value: 232.0
  }, {
    name: "Bosnia and Herzegovina",
    value: 189.0
  }, {
    name: "North Macedonia",
    value: 188.0
  }, {
    name: "Peru",
    value: 146.0
  }, {
    name: "Israel",
    value: 132.0
  }, {
    name: "Cameroon",
    value: 114.0
  }, {
    name: "Malaysia",
    value: 88.0
  }, {
    name: "Croatia",
    value: 79.0
  }, {
    name: "China, Taiwan Province of",
    value: 67.0
  }, {
    name: "Australia",
    value: 64.0
  }, {
    name: "Philippines",
    value: 49.0
  }, {
    name: "Lebanon",
    value: 47.0
  }, {
    name: "Cambodia",
    value: 43.0
  }, {
    name: "Malta",
    value: 38.0
  }, {
    name: "Democratic Republic of the Congo",
    value: 29.0
  }, {
    name: "C\\u00f4te d\'Ivoire",
    value: 27.0
  }, {
    name: "Iran (Islamic Republic of)",
    value: 27.0
  }, {
    name: "Mexico",
    value: 21.0
  }, {
    name: "Togo",
    value: 21.0
  }, {
    name: "Ethiopia",
    value: 19.0
  }, {
    name: "Luxembourg",
    value: 16.0
  }, {
    name: "Indonesia",
    value: 15.0
  }, {
    name: "China, Hong Kong SAR",
    value: 12.0
  }, {
    name: "Norway",
    value: 11.0
  }, {
    name: "Tunisia",
    value: 8.0
  }, {
    name: "Egypt",
    value: 7.0
  }, {
    name: "Zambia",
    value: 6.0
  }, {
    name: "Saudi Arabia",
    value: 6.0
  }, {
    name: "Cyprus",
    value: 5.0
  }, {
    name: "Syrian Arab Republic",
    value: 5.0
  }, {
    name: "Ghana",
    value: 4.0
  }, {
    name: "South Africa",
    value: 4.0
  }, {
    name: "United Arab Emirates",
    value: 4.0
  }, {
    name: "Montenegro",
    value: 3.0
  }, {
    name: "Colombia",
    value: 2.0
  }, {
    name: "Dominican Republic",
    value: 2.0
  }, {
    name: "Ecuador",
    value: 2.0
  }, {
    name: "Nigeria",
    value: 2.0
  }, {
    name: "Bangladesh",
    value: 2.0
  }, {
    name: "New Zealand",
    value: 1.0
  }, {
    name: "Morocco",
    value: 1.0
  }, {
    name: "Latvia",
    value: 1.0
  }, {
    name: "Kuwait",
    value: 1.0
  }, {
    name: "Jordan",
    value: 1.0
  }, {
    name: "Estonia",
    value: 1.0
  }, {
    name: "Armenia",
    value: 1.0
  }, {
    name: "Algeria",
    value: 1.0
  }];
  var alcohol = [
  {
    name: "Italy",
    value: 86320.0
  }, {
    name: "Germany",
    value: 64438.0
  }, {
    name: "France",
    value: 52252.0
  }, {
    name: "Spain",
    value: 33092.0
  }, {
    name: "Portugal",
    value: 31202.0
  }, {
    name: "Netherlands",
    value: 11773.0
  }, {
    name: "United States of America",
    value: 6154.0
  }, {
    name: "United Kingdom",
    value: 5821.0
  }, {
    name: "Mexico",
    value: 5594.0
  }, {
    name: "Austria",
    value: 5217.0
  }, {
    name: "South Africa",
    value: 4532.0
  }, {
    name: "Belgium",
    value: 4016.0
  }, {
    name: "Argentina",
    value: 3449.0
  }, {
    name: "Chile",
    value: 3062.0
  }, {
    name: "Ireland",
    value: 2867.0
  }, {
    name: "Australia",
    value: 2432.0
  }, {
    name: "Czechia",
    value: 2240.0
  }, {
    name: "Sweden",
    value: 898.0
  }, {
    name: "Thailand",
    value: 769.0
  }, {
    name: "Hungary",
    value: 556.0
  }, {
    name: "Cuba",
    value: 419.0
  }, {
    name: "China, mainland",
    value: 350.0
  }, {
    name: "Turkey",
    value: 324.0
  }, {
    name: "Canada",
    value: 309.0
  }, {
    name: "New Zealand",
    value: 280.0
  }, {
    name: "Denmark",
    value: 277.0
  }, {
    name: "Greece",
    value: 275.0
  }, {
    name: "Poland",
    value: 200.0
  }, {
    name: "Croatia",
    value: 178.0
  }, {
    name: "Slovenia",
    value: 171.0
  }, {
    name: "Serbia",
    value: 162.0
  }, {
    name: "Slovakia",
    value: 136.0
  }, {
    name: "Japan",
    value: 133.0
  }, {
    name: "Brazil",
    value: 117.0
  }, {
    name: "Dominican Republic",
    value: 82.0
  }, {
    name: "Russian Federation",
    value: 76.0
  }, {
    name: "Lebanon",
    value: 72.0
  }, {
    name: "Finland",
    value: 71.0
  }, {
    name: "Armenia",
    value: 71.0
  }, {
    name: "Latvia",
    value: 66.0
  }, {
    name: "Israel",
    value: 65.0
  }, {
    name: "Panama",
    value: 62.0
  }, {
    name: "Viet Nam",
    value: 61.0
  }, {
    name: "Romania",
    value: 57.0
  }, {
    name: "Jamaica",
    value: 51.0
  }, {
    name: "Republic of Moldova",
    value: 49.0
  }, {
    name: "North Macedonia",
    value: 48.0
  }, {
    name: "Venezuela (Bolivarian Republic of)",
    value: 46.0
  }, {
    name: "Peru",
    value: 45.0
  }, {
    name: "Norway",
    value: 37.0
  }, {
    name: "Sri Lanka",
    value: 35.0
  }, {
    name: "Ethiopia",
    value: 35.0
  }, {
    name: "Singapore",
    value: 34.0
  }, {
    name: "Bulgaria",
    value: 30.0
  }, {
    name: "Republic of Korea",
    value: 30.0
  }, {
    name: "Lithuania",
    value: 28.0
  }, {
    name: "Guatemala",
    value: 26.0
  }, {
    name: "Nigeria",
    value: 17.0
  }, {
    name: "Montenegro",
    value: 15.0
  }, {
    name: "Iran (Islamic Republic of)",
    value: 14.0
  }, {
    name: "Philippines",
    value: 13.0
  }, {
    name: "Iceland",
    value: 13.0
  }, {
    name: "Estonia",
    value: 13.0
  }, {
    name: "Bosnia and Herzegovina",
    value: 10.0
  }, {
    name: "Lao People\'s Democratic Republic",
    value: 10.0
  }, {
    name: "Morocco",
    value: 10.0
  }, {
    name: "Colombia",
    value: 9.0
  }, {
    name: "Ukraine",
    value: 8.0
  }, {
    name: "Barbados",
    value: 8.0
  }, {
    name: "Belarus",
    value: 8.0
  }, {
    name: "Palestine",
    value: 6.0
  }, {
    name: "India",
    value: 6.0
  }, {
    name: "Ecuador",
    value: 6.0
  }, {
    name: "Kenya",
    value: 5.0
  }, {
    name: "Georgia",
    value: 5.0
  }, {
    name: "Cameroon",
    value: 5.0
  }, {
    name: "Costa Rica",
    value: 4.0
  }, {
    name: "Luxembourg",
    value: 4.0
  }, {
    name: "Cyprus",
    value: 4.0
  }, {
    name: "China, Hong Kong SAR",
    value: 4.0
  }, {
    name: "Mongolia",
    value: 3.0
  }, {
    name: "Mauritius",
    value: 3.0
  }, {
    name: "Trinidad and Tobago",
    value: 2.0
  }, {
    name: "Indonesia",
    value: 2.0
  }, {
    name: "Bahamas",
    value: 2.0
  }, {
    name: "Madagascar",
    value: 1.0
  }, {
    name: "Seychelles",
    value: 1.0
  }, {
    name: "Guyana",
    value: 1.0
  }, {
    name: "Ghana",
    value: 1.0
  }, {
    name: "Faroe Islands",
    value: 1.0
  }, {
    name: "Cayman Islands",
    value: 1.0
  }, {
    name: "Togo",
    value: 1.0
  }, {
    name: "Albania",
    value: 1.0
  }, {
    name: "Bermuda",
    value: 1.0
  }];
  var fruits = [
  {
    name: "Spain",
    value: 186537.0
  }, {
    name: "Italy",
    value: 114899.0
  }, {
    name: "Colombia",
    value: 39563.0
  }, {
    name: "France",
    value: 34501.0
  }, {
    name: "Brazil",
    value: 29838.0
  }, {
    name: "Costa Rica",
    value: 22807.0
  }, {
    name: "South Africa",
    value: 22781.0
  }, {
    name: "Peru",
    value: 19651.0
  }, {
    name: "Panama",
    value: 19518.0
  }, {
    name: "Germany",
    value: 15776.0
  }, {
    name: "Ecuador",
    value: 14523.0
  }, {
    name: "Turkey",
    value: 9129.0
  }, {
    name: "Chile",
    value: 8749.0
  }, {
    name: "Netherlands",
    value: 8219.0
  }, {
    name: "Mexico",
    value: 7729.0
  }, {
    name: "Israel",
    value: 6975.0
  }, {
    name: "Dominican Republic",
    value: 6078.0
  }, {
    name: "United States of America",
    value: 5469.0
  }, {
    name: "Thailand",
    value: 5409.0
  }, {
    name: "Greece",
    value: 5217.0
  }, {
    name: "Morocco",
    value: 4987.0
  }, {
    name: "New Zealand",
    value: 4908.0
  }, {
    name: "Serbia",
    value: 4387.0
  }, {
    name: "United Kingdom",
    value: 4281.0
  }, {
    name: "Poland",
    value: 4161.0
  }, {
    name: "Belgium",
    value: 3929.0
  }, {
    name: "Austria",
    value: 3530.0
  }, {
    name: "India",
    value: 3289.0
  }, {
    name: "Portugal",
    value: 2981.0
  }, {
    name: "Ghana",
    value: 2755.0
  }, {
    name: "China, mainland",
    value: 2294.0
  }, {
    name: "Hungary",
    value: 1974.0
  }, {
    name: "Argentina",
    value: 1846.0
  }, {
    name: "Indonesia",
    value: 1800.0
  }, {
    name: "Egypt",
    value: 1689.0
  }, {
    name: "Tunisia",
    value: 1619.0
  }, {
    name: "C\\u00f4te d\'Ivoire",
    value: 1335.0
  }, {
    name: "Viet Nam",
    value: 1058.0
  }, {
    name: "Bosnia and Herzegovina",
    value: 880.0
  }, {
    name: "Honduras",
    value: 858.0
  }, {
    name: "Senegal",
    value: 717.0
  }, {
    name: "Canada",
    value: 701.0
  }, {
    name: "Madagascar",
    value: 454.0
  }, {
    name: "Uruguay",
    value: 445.0
  }, {
    name: "Belarus",
    value: 401.0
  }, {
    name: "Sweden",
    value: 379.0
  }, {
    name: "Cameroon",
    value: 365.0
  }, {
    name: "Ukraine",
    value: 324.0
  }, {
    name: "North Macedonia",
    value: 302.0
  }, {
    name: "Bulgaria",
    value: 275.0
  }, {
    name: "Philippines",
    value: 269.0
  }, {
    name: "Australia",
    value: 251.0
  }, {
    name: "Sri Lanka",
    value: 238.0
  }, {
    name: "Kenya",
    value: 230.0
  }, {
    name: "Iran (Islamic Republic of)",
    value: 227.0
  }, {
    name: "Burkina Faso",
    value: 204.0
  }, {
    name: "Pakistan",
    value: 188.0
  }, {
    name: "Malaysia",
    value: 185.0
  }, {
    name: "Guatemala",
    value: 168.0
  }, {
    name: "Zimbabwe",
    value: 156.0
  }, {
    name: "Mauritius",
    value: 154.0
  }, {
    name: "Albania",
    value: 139.0
  }, {
    name: "Namibia",
    value: 123.0
  }, {
    name: "China, Taiwan Province of",
    value: 118.0
  }, {
    name: "Denmark",
    value: 113.0
  }, {
    name: "Cuba",
    value: 108.0
  }, {
    name: "Uganda",
    value: 102.0
  }, {
    name: "Czechia",
    value: 100.0
  }, {
    name: "Jamaica",
    value: 85.0
  }, {
    name: "Eswatini",
    value: 82.0
  }, {
    name: "Romania",
    value: 76.0
  }, {
    name: "Algeria",
    value: 62.0
  }, {
    name: "Paraguay",
    value: 55.0
  }, {
    name: "Saudi Arabia",
    value: 52.0
  }, {
    name: "Benin",
    value: 46.0
  }, {
    name: "Mali",
    value: 46.0
  }, {
    name: "Ireland",
    value: 44.0
  }, {
    name: "Togo",
    value: 37.0
  }, {
    name: "Japan",
    value: 34.0
  }, {
    name: "Western Sahara",
    value: 33.0
  }, {
    name: "United Republic of Tanzania",
    value: 27.0
  }, {
    name: "Republic of Moldova",
    value: 21.0
  }, {
    name: "Estonia",
    value: 16.0
  }, {
    name: "Republic of Korea",
    value: 15.0
  }, {
    name: "Iceland",
    value: 12.0
  }, {
    name: "Lebanon",
    value: 11.0
  }, {
    name: "Belize",
    value: 11.0
  }, {
    name: "Guinea",
    value: 10.0
  }, {
    name: "Cyprus",
    value: 10.0
  }, {
    name: "Palestine",
    value: 9.0
  }, {
    name: "Finland",
    value: 8.0
  }, {
    name: "Lao People\'s Democratic Republic",
    value: 8.0
  }, {
    name: "Gambia",
    value: 7.0
  }, {
    name: "United Arab Emirates",
    value: 6.0
  }, {
    name: "Trinidad and Tobago",
    value: 5.0
  }, {
    name: "Lithuania",
    value: 5.0
  }, {
    name: "Mozambique",
    value: 5.0
  }, {
    name: "French Polynesia",
    value: 4.0
  }, {
    name: "Slovakia",
    value: 4.0
  }, {
    name: "Slovenia",
    value: 4.0
  }, {
    name: "Uzbekistan",
    value: 4.0
  }, {
    name: "Montenegro",
    value: 4.0
  }, {
    name: "Croatia",
    value: 4.0
  }, {
    name: "Papua New Guinea",
    value: 2.0
  }, {
    name: "Jordan",
    value: 2.0
  }, {
    name: "Iraq",
    value: 2.0
  }, {
    name: "Georgia",
    value: 1.0
  }, {
    name: "Ethiopia",
    value: 1.0
  }, {
    name: "Bolivia (Plurinational State of)",
    value: 1.0
  }, {
    name: "Singapore",
    value: 1.0
  }, {
    name: "Tonga",
    value: 1.0
  }, {
    name: "Nicaragua",
    value: 1.0
  }, {
    name: "Nigeria",
    value: 1.0
  }];
  var meat = [
  {
    name: "Germany",
    value: 21271.0
  }, {
    name: "Brazil",
    value: 18789.0
  }, {
    name: "France",
    value: 9536.0
  }, {
    name: "Austria",
    value: 8518.0
  }, {
    name: "Hungary",
    value: 6600.0
  }, {
    name: "Italy",
    value: 6435.0
  }, {
    name: "Ireland",
    value: 4234.0
  }, {
    name: "Netherlands",
    value: 3904.0
  }, {
    name: "Australia",
    value: 3151.0
  }, {
    name: "New Zealand",
    value: 2799.0
  }, {
    name: "Slovenia",
    value: 2652.0
  }, {
    name: "Uruguay",
    value: 1445.0
  }, {
    name: "Paraguay",
    value: 1384.0
  }, {
    name: "Spain",
    value: 1302.0
  }, {
    name: "Poland",
    value: 1273.0
  }, {
    name: "United Kingdom",
    value: 1213.0
  }, {
    name: "Argentina",
    value: 1186.0
  }, {
    name: "Thailand",
    value: 907.0
  }, {
    name: "Belgium",
    value: 758.0
  }, {
    name: "Portugal",
    value: 607.0
  }, {
    name: "Canada",
    value: 575.0
  }, {
    name: "United States of America",
    value: 489.0
  }, {
    name: "Croatia",
    value: 412.0
  }, {
    name: "Czechia",
    value: 335.0
  }, {
    name: "South Africa",
    value: 333.0
  }, {
    name: "Denmark",
    value: 225.0
  }, {
    name: "Romania",
    value: 174.0
  }, {
    name: "China, mainland",
    value: 142.0
  }, {
    name: "Ukraine",
    value: 141.0
  }, {
    name: "Iceland",
    value: 59.0
  }, {
    name: "Indonesia",
    value: 49.0
  }, {
    name: "Lithuania",
    value: 34.0
  }, {
    name: "Sweden",
    value: 28.0
  }, {
    name: "Chile",
    value: 26.0
  }, {
    name: "Bulgaria",
    value: 22.0
  }, {
    name: "Estonia",
    value: 18.0
  }, {
    name: "Russian Federation",
    value: 13.0
  }, {
    name: "Slovakia",
    value: 10.0
  }, {
    name: "Serbia",
    value: 8.0
  }, {
    name: "Greece",
    value: 7.0
  }, {
    name: "Namibia",
    value: 7.0
  }, {
    name: "Niger",
    value: 7.0
  }, {
    name: "North Macedonia",
    value: 6.0
  }, {
    name: "Japan",
    value: 3.0
  }, {
    name: "United Arab Emirates",
    value: 2.0
  }, {
    name: "Zimbabwe",
    value: 1.0
  }, {
    name: "China, Taiwan Province of",
    value: 1.0
  }];
  var dairy = [
  {
    name: "France",
    value: 41556.0
  }, {
    name: "Germany",
    value: 32123.0
  }, {
    name: "Italy",
    value: 22029.0
  }, {
    name: "Netherlands",
    value: 4576.0
  }, {
    name: "Belgium",
    value: 4043.0
  }, {
    name: "United States of America",
    value: 2742.0
  }, {
    name: "Austria",
    value: 2500.0
  }, {
    name: "Greece",
    value: 1951.0
  }, {
    name: "Denmark",
    value: 1494.0
  }, {
    name: "Spain",
    value: 908.0
  }, {
    name: "Iceland",
    value: 734.0
  }, {
    name: "Portugal",
    value: 700.0
  }, {
    name: "United Kingdom",
    value: 665.0
  }, {
    name: "Poland",
    value: 456.0
  }, {
    name: "Lithuania",
    value: 323.0
  }, {
    name: "Hungary",
    value: 256.0
  }, {
    name: "Slovenia",
    value: 239.0
  }, {
    name: "Ireland",
    value: 183.0
  }, {
    name: "Russian Federation",
    value: 129.0
  }, {
    name: "Czechia",
    value: 82.0
  }, {
    name: "Cyprus",
    value: 70.0
  }, {
    name: "Sweden",
    value: 50.0
  }, {
    name: "North Macedonia",
    value: 24.0
  }, {
    name: "Finland",
    value: 24.0
  }, {
    name: "New Zealand",
    value: 22.0
  }, {
    name: "Bosnia and Herzegovina",
    value: 12.0
  }, {
    name: "Bulgaria",
    value: 11.0
  }, {
    name: "Slovakia",
    value: 10.0
  }, {
    name: "Thailand",
    value: 6.0
  }, {
    name: "Croatia",
    value: 3.0
  }, {
    name: "Iran (Islamic Republic of)",
    value: 2.0
  }, {
    name: "Romania",
    value: 2.0
  }, {
    name: "Brazil",
    value: 1.0
  }, {
    name: "Japan",
    value: 1.0
  }];
  var starchy = [
  {
    name: "Netherlands",
    value: 20354.0
  }, {
    name: "Germany",
    value: 13088.0
  }, {
    name: "France",
    value: 6944.0
  }, {
    name: "Israel",
    value: 5052.0
  }, {
    name: "Spain",
    value: 4861.0
  }, {
    name: "Austria",
    value: 3453.0
  }, {
    name: "Egypt",
    value: 3380.0
  }, {
    name: "Belgium",
    value: 2785.0
  }, {
    name: "United States of America",
    value: 1816.0
  }, {
    name: "Italy",
    value: 1385.0
  }, {
    name: "Cyprus",
    value: 1054.0
  }, {
    name: "Costa Rica",
    value: 553.0
  }, {
    name: "Honduras",
    value: 341.0
  }, {
    name: "Portugal",
    value: 338.0
  }, {
    name: "Thailand",
    value: 283.0
  }, {
    name: "Poland",
    value: 94.0
  }, {
    name: "Denmark",
    value: 76.0
  }, {
    name: "Senegal",
    value: 71.0
  }, {
    name: "Ecuador",
    value: 55.0
  }, {
    name: "Slovenia",
    value: 49.0
  }, {
    name: "Brazil",
    value: 38.0
  }, {
    name: "Ghana",
    value: 36.0
  }, {
    name: "China, mainland",
    value: 35.0
  }, {
    name: "Uganda",
    value: 32.0
  }, {
    name: "Togo",
    value: 28.0
  }, {
    name: "Andorra",
    value: 25.0
  }, {
    name: "Pakistan",
    value: 24.0
  }, {
    name: "Malta",
    value: 23.0
  }, {
    name: "Iceland",
    value: 22.0
  }, {
    name: "Morocco",
    value: 19.0
  }, {
    name: "Cameroon",
    value: 18.0
  }, {
    name: "India",
    value: 17.0
  }, {
    name: "United Kingdom",
    value: 16.0
  }, {
    name: "Nigeria",
    value: 14.0
  }, {
    name: "South Africa",
    value: 12.0
  }, {
    name: "Turkey",
    value: 10.0
  }, {
    name: "Viet Nam",
    value: 10.0
  }, {
    name: "Nicaragua",
    value: 8.0
  }, {
    name: "Sweden",
    value: 6.0
  }, {
    name: "C\\u00f4te d\'Ivoire",
    value: 2.0
  }, {
    name: "Peru",
    value: 2.0
  }, {
    name: "Chile",
    value: 2.0
  }, {
    name: "Sri Lanka",
    value: 1.0
  }, {
    name: "Niger",
    value: 1.0
  }, {
    name: "Hungary",
    value: 1.0
  }, {
    name: "Guatemala",
    value: 1.0
  }, {
    name: "Colombia",
    value: 1.0
  }];
  var sugar = [
  {
    name: "Germany",
    value: 104324.0
  }, {
    name: "Italy",
    value: 92243.0
  }, {
    name: "France",
    value: 84355.0
  }, {
    name: "Austria",
    value: 70960.0
  }, {
    name: "Czechia",
    value: 41830.0
  }, {
    name: "Netherlands",
    value: 18030.0
  }, {
    name: "Belgium",
    value: 9340.0
  }, {
    name: "Poland",
    value: 5838.0
  }, {
    name: "Portugal",
    value: 5577.0
  }, {
    name: "Denmark",
    value: 4871.0
  }, {
    name: "United Kingdom",
    value: 4363.0
  }, {
    name: "Turkey",
    value: 4168.0
  }, {
    name: "Paraguay",
    value: 3951.0
  }, {
    name: "Costa Rica",
    value: 3454.0
  }, {
    name: "Spain",
    value: 2997.0
  }, {
    name: "Hungary",
    value: 2959.0
  }, {
    name: "Mexico",
    value: 2755.0
  }, {
    name: "Bulgaria",
    value: 2549.0
  }, {
    name: "China, mainland",
    value: 2423.0
  }, {
    name: "Mauritius",
    value: 2376.0
  }, {
    name: "Ireland",
    value: 2310.0
  }, {
    name: "Argentina",
    value: 2087.0
  }, {
    name: "Bosnia and Herzegovina",
    value: 1708.0
  }, {
    name: "Thailand",
    value: 1680.0
  }, {
    name: "Slovakia",
    value: 1522.0
  }, {
    name: "Sweden",
    value: 1186.0
  }, {
    name: "China, Taiwan Province of",
    value: 969.0
  }, {
    name: "United States of America",
    value: 901.0
  }, {
    name: "Colombia",
    value: 870.0
  }, {
    name: "Serbia",
    value: 632.0
  }, {
    name: "Slovenia",
    value: 561.0
  }, {
    name: "Canada",
    value: 499.0
  }, {
    name: "Cuba",
    value: 497.0
  }, {
    name: "North Macedonia",
    value: 472.0
  }, {
    name: "Brazil",
    value: 453.0
  }, {
    name: "Morocco",
    value: 316.0
  }, {
    name: "Croatia",
    value: 271.0
  }, {
    name: "Chile",
    value: 250.0
  }, {
    name: "Indonesia",
    value: 216.0
  }, {
    name: "El Salvador",
    value: 200.0
  }, {
    name: "Philippines",
    value: 181.0
  }, {
    name: "Greece",
    value: 178.0
  }, {
    name: "Luxembourg",
    value: 135.0
  }, {
    name: "Guatemala",
    value: 127.0
  }, {
    name: "Egypt",
    value: 111.0
  }, {
    name: "Republic of Korea",
    value: 88.0
  }, {
    name: "Romania",
    value: 84.0
  }, {
    name: "Uruguay",
    value: 80.0
  }, {
    name: "Malaysia",
    value: 75.0
  }, {
    name: "Eswatini",
    value: 75.0
  }, {
    name: "Ukraine",
    value: 57.0
  }, {
    name: "Finland",
    value: 57.0
  }, {
    name: "Japan",
    value: 56.0
  }, {
    name: "Sri Lanka",
    value: 52.0
  }, {
    name: "Albania",
    value: 52.0
  }, {
    name: "Singapore",
    value: 51.0
  }, {
    name: "Pakistan",
    value: 49.0
  }, {
    name: "India",
    value: 44.0
  }, {
    name: "Malawi",
    value: 40.0
  }, {
    name: "Dominican Republic",
    value: 33.0
  }, {
    name: "United Arab Emirates",
    value: 30.0
  }, {
    name: "Peru",
    value: 26.0
  }, {
    name: "Tunisia",
    value: 25.0
  }, {
    name: "Bangladesh",
    value: 20.0
  }, {
    name: "Israel",
    value: 18.0
  }, {
    name: "Australia",
    value: 18.0
  }, {
    name: "Nigeria",
    value: 17.0
  }, {
    name: "Algeria",
    value: 14.0
  }, {
    name: "South Africa",
    value: 14.0
  }, {
    name: "New Zealand",
    value: 14.0
  }, {
    name: "Lithuania",
    value: 13.0
  }, {
    name: "Russian Federation",
    value: 12.0
  }, {
    name: "Iran (Islamic Republic of)",
    value: 12.0
  }, {
    name: "Ghana",
    value: 10.0
  }, {
    name: "Latvia",
    value: 10.0
  }, {
    name: "Viet Nam",
    value: 9.0
  }, {
    name: "Saudi Arabia",
    value: 9.0
  }, {
    name: "Lebanon",
    value: 8.0
  }, {
    name: "Cameroon",
    value: 8.0
  }, {
    name: "Cyprus",
    value: 4.0
  }, {
    name: "China, Hong Kong SAR",
    value: 4.0
  }, {
    name: "Togo",
    value: 3.0
  }, {
    name: "Nicaragua",
    value: 3.0
  }, {
    name: "China, Macao SAR",
    value: 3.0
  }, {
    name: "Armenia",
    value: 2.0
  }, {
    name: "Democratic Republic of the Congo",
    value: 1.0
  }, {
    name: "Niger",
    value: 1.0
  }, {
    name: "Republic of Moldova",
    value: 1.0
  }, {
    name: "Senegal",
    value: 1.0
  }];
  var vegetables = [
  {
    name: "Spain",
    value: 110014.0
  }, {
    name: "Italy",
    value: 90179.0
  }, {
    name: "Netherlands",
    value: 23010.0
  }, {
    name: "France",
    value: 15303.0
  }, {
    name: "Germany",
    value: 14745.0
  }, {
    name: "Morocco",
    value: 12443.0
  }, {
    name: "Turkey",
    value: 9259.0
  }, {
    name: "Belgium",
    value: 9208.0
  }, {
    name: "China, mainland",
    value: 6896.0
  }, {
    name: "Hungary",
    value: 5164.0
  }, {
    name: "Poland",
    value: 4701.0
  }, {
    name: "Portugal",
    value: 4374.0
  }, {
    name: "Thailand",
    value: 4025.0
  }, {
    name: "Austria",
    value: 3419.0
  }, {
    name: "India",
    value: 2233.0
  }, {
    name: "United States of America",
    value: 1583.0
  }, {
    name: "Peru",
    value: 1328.0
  }, {
    name: "Mexico",
    value: 1214.0
  }, {
    name: "North Macedonia",
    value: 1117.0
  }, {
    name: "Ukraine",
    value: 926.0
  }, {
    name: "Egypt",
    value: 710.0
  }, {
    name: "Greece",
    value: 642.0
  }, {
    name: "United Kingdom",
    value: 579.0
  }, {
    name: "Sri Lanka",
    value: 536.0
  }, {
    name: "Kenya",
    value: 509.0
  }, {
    name: "Denmark",
    value: 504.0
  }, {
    name: "Senegal",
    value: 403.0
  }, {
    name: "Serbia",
    value: 391.0
  }, {
    name: "Viet Nam",
    value: 358.0
  }, {
    name: "South Africa",
    value: 319.0
  }, {
    name: "Ecuador",
    value: 304.0
  }, {
    name: "Bosnia and Herzegovina",
    value: 280.0
  }, {
    name: "Lithuania",
    value: 258.0
  }, {
    name: "Dominican Republic",
    value: 254.0
  }, {
    name: "Sweden",
    value: 244.0
  }, {
    name: "Tunisia",
    value: 229.0
  }, {
    name: "Lebanon",
    value: 214.0
  }, {
    name: "New Zealand",
    value: 209.0
  }, {
    name: "Belarus",
    value: 203.0
  }, {
    name: "Israel",
    value: 182.0
  }, {
    name: "Romania",
    value: 127.0
  }, {
    name: "Guatemala",
    value: 112.0
  }, {
    name: "Republic of Korea",
    value: 98.0
  }, {
    name: "Albania",
    value: 96.0
  }, {
    name: "Uganda",
    value: 93.0
  }, {
    name: "Russian Federation",
    value: 89.0
  }, {
    name: "Czechia",
    value: 84.0
  }, {
    name: "Argentina",
    value: 74.0
  }, {
    name: "Bulgaria",
    value: 73.0
  }, {
    name: "Japan",
    value: 58.0
  }, {
    name: "Costa Rica",
    value: 45.0
  }, {
    name: "Honduras",
    value: 45.0
  }, {
    name: "Chile",
    value: 44.0
  }, {
    name: "Canada",
    value: 42.0
  }, {
    name: "Croatia",
    value: 38.0
  }, {
    name: "Togo",
    value: 35.0
  }, {
    name: "Cameroon",
    value: 35.0
  }, {
    name: "Zimbabwe",
    value: 33.0
  }, {
    name: "Montenegro",
    value: 31.0
  }, {
    name: "Slovenia",
    value: 27.0
  }, {
    name: "China, Taiwan Province of",
    value: 23.0
  }, {
    name: "Pakistan",
    value: 22.0
  }, {
    name: "Australia",
    value: 17.0
  }, {
    name: "Brazil",
    value: 15.0
  }, {
    name: "Cyprus",
    value: 14.0
  }, {
    name: "Iran (Islamic Republic of)",
    value: 13.0
  }, {
    name: "Nigeria",
    value: 9.0
  }, {
    name: "United Arab Emirates",
    value: 9.0
  }, {
    name: "Malaysia",
    value: 9.0
  }, {
    name: "United Republic of Tanzania",
    value: 7.0
  }, {
    name: "Saudi Arabia",
    value: 7.0
  }, {
    name: "Latvia",
    value: 5.0
  }, {
    name: "Uzbekistan",
    value: 5.0
  }, {
    name: "Ethiopia",
    value: 5.0
  }, {
    name: "Democratic Republic of the Congo",
    value: 5.0
  }, {
    name: "Armenia",
    value: 5.0
  }, {
    name: "Estonia",
    value: 4.0
  }, {
    name: "Bangladesh",
    value: 4.0
  }, {
    name: "Jordan",
    value: 4.0
  }, {
    name: "Ghana",
    value: 3.0
  }, {
    name: "Indonesia",
    value: 3.0
  }, {
    name: "Mongolia",
    value: 3.0
  }, {
    name: "Mozambique",
    value: 3.0
  }, {
    name: "Nicaragua",
    value: 3.0
  }, {
    name: "Slovakia",
    value: 3.0
  }, {
    name: "Eswatini",
    value: 3.0
  }, {
    name: "Algeria",
    value: 2.0
  }, {
    name: "Ireland",
    value: 2.0
  }, {
    name: "Rwanda",
    value: 1.0
  }, {
    name: "Uruguay",
    value: 1.0
  }, {
    name: "Syrian Arab Republic",
    value: 1.0
  }, {
    name: "Suriname",
    value: 1.0
  }, {
    name: "Philippines",
    value: 1.0
  }, {
    name: "Namibia",
    value: 1.0
  }, {
    name: "Malta",
    value: 1.0
  }, {
    name: "Finland",
    value: 1.0
  }];
  // Initiate the chart

  var chartmap = Highcharts.mapChart('import_map', {

    chart: {
      map: 'custom/world'
    },

    mapNavigation: {
      enabled: true,
      enableDoubleClickZoomTo: true
    },

    title: {
      text: '2017 Switzerland imports'
    },

    subtitle: {
      text: 'Overview'
    },

    colorAxis: {
      dataClasses: [{
        to: 1,
        color: '#3498DB',
        name: 'Alcohol'
      }, {
        from: 1,
        to: 2,
        color: '#34495E',
        name: 'Cereals'
      }, {
        from: 2,
        to: 3,
        color: '#2ECC71',
        name: 'Fruits'
      }, {
        from: 3,
        to: 4,
        color: '#E67E22',
        name: 'Meat'
      }, {
        from: 4,
        to: 5,
        color: '#9B59B6',
        name: 'Dairy'
      }, {
        from: 5,
        to: 6,
        color: '#E9129E',
        name: 'Potatoes'
      }, {
        from: 6,
        to: 7,
        color: '#F1C40F',
        name: 'Sugar'
      }, {
        from: 8,
        color: '#16A085',
        name: 'Vegetables'
      }]
    },
    series: [{
      data: [{
        name: "France",
        value: 4.0
      }, {
        name: "Spain",
        value: 7.0
      }, {
        name: "Netherlands",
        value: 5.0
      }, {
        name: "Germany",
        value: 1.0
      }, {
        name: "Italy",
        value: 7.0
      }, {
        name: "Brazil",
        value: 3.0
      }, {
        name: "Austria",
        value: 6.0
      }, {
        name: "Portugal",
        value: 0.0
      }, {
        name: "Czechia",
        value: 6.0
      }, {
        name: "Israel",
        value: 5.0
      }, {
        name: "Hungary",
        value: 3.0
      }, {
        name: "Colombia",
        value: 2.0
      }, {
        name: "Egypt",
        value: 5.0
      }, {
        name: "Canada",
        value: 1.0
      }, {
        name: "Slovakia",
        value: 1.0
      }, {
        name: "Belgium",
        value: 5.0
      }, {
        name: "Ireland",
        value: 3.0
      }, {
        name: "Morocco",
        value: 7.0
      }, {
        name: "Costa Rica",
        value: 2.0
      }, {
        name: "South Africa",
        value: 2.0
      }, {
        name: "Australia",
        value: 3.0
      }, {
        name: "Peru",
        value: 2.0
      }, {
        name: "Panama",
        value: 2.0
      }, {
        name: "Turkey",
        value: 7.0
      }, {
        name: "New Zealand",
        value: 3.0
      }],
      joinBy: ['name', 'name'],
      name: 'Item Group',
      states: {
        hover: {
          color: '#a4edba'
        }
      }
    }]
  });

  $('#overview').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Overview'
      },
      colorAxis: {
        dataClasses: [{
          to: 1,
          color: '#3498DB',
          name: 'Alcohol'
        }, {
          from: 1,
          to: 2,
          color: '#34495E',
          name: 'Cereals'
        }, {
          from: 2,
          to: 3,
          color: '#2ECC71',
          name: 'Fruits'
        }, {
          from: 3,
          to: 4,
          color: '#E67E22',
          name: 'Meat'
        }, {
          from: 4,
          to: 5,
          color: '#9B59B6',
          name: 'Dairy'
        }, {
          from: 5,
          to: 6,
          color: '#E9129E',
          name: 'Potatoes'
        }, {
          from: 6,
          to: 7,
          color: '#F1C40F',
          name: 'Sugar'
        }, {
          from: 8,
          color: '#16A085',
          name: 'Vegetables'
        }],
        min: false,
        max: false,
        type: false,
        minColor: false,
        maxColor: false,
      },
      series: [{
        data: overview,
        joinBy: ['name', 'name'],
        name: 'Item Group',
        states: {
          hover: {
            color: '#a4edba'
          }
        },
        tooltip: {
          valueSuffix: ''
        }
      }]
    });
  });
  $('#alcohol').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Alcoholic beverages'
      },

      colorAxis: {
        dataClasses: false,
        min: 1000,
        max: 100000,
        type: 'logarithmic',
        minColor: '#EAF2F8',
        maxColor: '#154360',
      },
      tooltip: {
        valueSuffix: ' tonnes'
      },
      series: [{
        data: alcohol,
        joinBy: ['name', 'name'],
        name: 'Importation Quantity',
        states: {
          hover: {
            color: '#a4edba'
          }
        },

      }]
    });
  });

  $('#cereals').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Cereals'
      },


      colorAxis: {
        dataClasses: false,
        min: 1000,
        max: 300000,
        type: 'logarithmic',
        minColor: '#EBEDEF',
        maxColor: '#1C2833',
      },
      tooltip: {
        valueSuffix: ' tonnes'
      },
      series: [{
        data: cereals,
        joinBy: ['name', 'name'],
        name: 'Importation Quantity',
        states: {
          hover: {
            color: '#a4edba'
          }
        },
        tooltip: {
          valueSuffix: ' tonnes'
        }
      }]
    });
  });

  $('#fruits').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Fruits'
      },

      colorAxis: {
        dataClasses: false,
        min: 1000,
        max: 100000,
        type: 'logarithmic',
        minColor: '#EAFAF1',
        maxColor: '#186A3B',
      },

      series: [{
        data: fruits,
        joinBy: ['name', 'name'],
        name: 'Importation Quantity',
        states: {
          hover: {
            color: '#a4edba'
          }
        },
        tooltip: {
          valueSuffix: ' tonnes'
        }
      }]
    });
  });

  $('#meat').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Meat'
      },

      colorAxis: {
        dataClasses: false,
        min: 1000,
        max: 20000,
        type: 'logarithmic',
        minColor: '#F6DDCC',
        maxColor: '#6E2C00',
      },

      series: [{
        data: meat,
        joinBy: ['name', 'name'],
        name: 'Importation Quantity',
        states: {
          hover: {
            color: '#a4edba'
          }
        },
        tooltip: {
          valueSuffix: ' tonnes'
        }
      }]
    });
  });

  $('#dairy').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Dairy products'
      },

      colorAxis: {
        dataClasses: false,
        min: 1000,
        max: 50000,
        type: 'logarithmic',
        minColor: '#F5EEF8',
        maxColor: '#512E5F',
      },

      series: [{
        data: dairy,
        joinBy: ['name', 'name'],
        name: 'Importation Quantity',
        states: {
          hover: {
            color: '#a4edba'
          }
        },
        tooltip: {
          valueSuffix: ' tonnes'
        }
      }]
    });
  });

  $('#starchy').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Potatoes (Starchy Roots)'
      },

      colorAxis: {
        dataClasses: false,
        min: 1000,
        max: 10000,
        type: 'logarithmic',
        minColor: '#FFEDF7',
        maxColor: '#5E0438',
      },

      series: [{
        data: starchy,
        joinBy: ['name', 'name'],
        name: 'Importation Quantity',
        states: {
          hover: {
            color: '#a4edba'
          }
        },
        tooltip: {
          valueSuffix: ' tonnes'
        }
      }]
    });
  });

  $('#sugar').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Sugar & Sweeteners'
      },

      colorAxis: {
        dataClasses: false,
        min: 1000,
        max: 100000,
        type: 'logarithmic',
        minColor: '#FEF9E7',
        maxColor: '#7D6608',
      },

      series: [{
        data: sugar,
        joinBy: ['name', 'name'],
        name: 'Importation Quantity',
        states: {
          hover: {
            color: '#a4edba'
          }
        },
        tooltip: {
          valueSuffix: ' tonnes'
        }
      }]
    });
  });

  $('#vegetables').click(function() {
    chartmap.update({

      subtitle: {
        text: 'Vegetables'
      },

      colorAxis: {
        dataClasses: false,
        min: 1000,
        max: 100000,
        type: 'logarithmic',
        minColor: '#E8F6F3',
        maxColor: '#0B5345',
      },

      series: [{
        data: vegetables,
        joinBy: ['name', 'name'],
        name: 'Importation Quantity',
        states: {
          hover: {
            color: '#a4edba'
          }
        },
        tooltip: {
          valueSuffix: ' tonnes'
        }
      }]
    });
  });

  var colors = Highcharts.getOptions().colors;
  Highcharts.chart('prod_price_maize', {

    chart: {
      type: 'streamgraph',
    },

    // Make sure connected countries have similar colors
    colors: [
      colors[1],
      colors[9],
      colors[7],
      colors[3],
      colors[4]
    ],

    title: {
      floating: true,
      align: 'left',
      text: 'Proportion of producer prices of Maize by country group'
    },

    xAxis: {
      maxPadding: 0,
      type: 'category',
      crosshair: true,
      categories: [
        '',
        '1991',
        '1992',
        '1993',
        '1994',
        '1995',
        '1996',
        '1997',
        '1998',
        '1999',
        '2000',
        '2000',
        '2001',
        '2002',
        '2003',
        '2004',
        '2005',
        '2006',
        '2007',
        '2008',
        '2009',
        '2010',
        '2011',
        '2012',
        '2013',
        '2014',
        '2015',
        '2016',
        '2017',
        '2018',
      ],
      labels: {
        align: 'left',
        reserveSpace: false,
        rotation: 270
      },
      lineWidth: 0,
      margin: 20,
      tickWidth: 0
    },

    yAxis: {
      visible: false,
      title: {
        text: 'Production price (USD)'
      }
    },

    tooltip: {
      split: true,
      valueDecimals: 2,
      valueSuffix: 'USD'
    },
    plotOptions: {
      series: {
        label: {
          minFontSize: 5,
          maxFontSize: 15,
          style: {
            color: 'rgba(255,255,255,0.75)'
          }
        }
      }
    },

    // Data parsed with olympic-medals.node.js
    series: [{
      name: "Switzerland",
      data: [523., 533.3, 487.3, 489.9, 509.9, 436.1, 364.5, 358.7, 330.2,
        283.6, 263.7, 285.5, 344.6, 309.6, 278.7, 300.7, 299.1, 314.8,
        292.2, 320.3, 343.5, 319.9, 342., 322., 328.4, 320.7, 314.8,
        340.5
      ]
    }, {
      name: "High-income economies",
      data: [221.0952381, 212.69545455, 226.77692308, 224.72222222,
        276.62962963, 284.07407407, 237.47777778, 213.96296296,
        185.11111111, 169.00357143, 159.33928571, 156.16551724,
        184.08333333, 181.5, 172.14482759, 189.74642857,
        265.99259259, 267.36923077, 283.73571429, 335.04230769,
        352.17307692, 347.2037037, 337.54230769, 314.30357143,
        361.18214286, 338.78928571, 324.61785714, 349.21538462
      ]
    }, {
      name: "Upper-middle-income economies",
      data: [223.78636364, 239.46666667, 244.22962963, 227.45357143,
        232.80967742, 258.37666667, 274.95333333, 275.91515152,
        260.32727273, 253.12424242, 236.41515152, 228.63939394,
        248.4030303, 265.734375, 264.62258065, 298.7875,
        356.9875, 461.02121212, 409.24193548, 473.04193548,
        517.05151515, 489.35588235, 512.98484848, 512.27272727,
        512.54375, 465.57333333, 481.38928571, 512.12307692
      ]
    }, {
      name: "Lower-middle-income economies",
      data: [176.91052632, 184.555, 174.26842105, 186.24761905,
        183.93478261, 192.1, 210.5875, 193.244,
        189.52608696, 183.85833333, 186.16538462, 185.66153846,
        207.828, 219.91304348, 232.26666667, 231.91538462,
        291.51666667, 364.92222222, 362.08148148, 356.43461538,
        413.31538462, 415.94, 382.00952381, 314.50555556,
        285.92352941, 327.5625, 276.53333333, 296.1
      ]
    }, {
      name: "Low income economies",
      data: [232.15, 212.15, 189.98125, 177.09444444,
        222.34736842, 201.92222222, 200.55882353, 214.47222222,
        177.2, 149.76666667, 149.97777778, 202.63684211,
        205.12222222, 238.78, 284.34285714, 268.74375,
        305.08823529, 410.03333333, 348.77142857, 312.36875,
        385.14375, 396.53125, 419.30714286, 366.51666667,
        394.63636364, 362.18571429, 303.46923077, 229.15555556
      ]
    }],

    exporting: {
      sourceWidth: 800,
      sourceHeight: 600
    }

  });

  Highcharts.chart('maize_price_evo', {

    title: {
      text: 'Maize price evolution by country group, 1991-2018'
    },

    yAxis: {
      title: {
        text: 'Percentage change from 1991 (%)'
      }
    },


    xAxis: {
      accessibility: {
        rangeDescription: 'Range: 1991 to 2018',
        dashStyle: 'dash'
      },
      title: {
        text: 'Year'
      }
    },

    tooltip: {
      split: true,
      valueDecimals: 2,
      valueSuffix: '%'
    },
    plotOptions: {
      series: {
        marker: {
          enabled: false
        },
        label: {
          enabled: false
        },
        pointStart: 1991
      }
    },

    series: [{
      name: 'Switzerland',
      data: [0., 1.96940727, -6.82600382, -6.32887189,
        -2.50478011, -16.61567878, -30.30592734, -31.41491396,
        -36.86424474, -45.77437859, -49.5793499, -45.41108987,
        -34.11089866, -40.80305927, -46.71128107, -42.50478011,
        -42.81070746, -39.80879541, -44.13001912, -38.75717017,
        -34.32122371, -38.83365201, -34.60803059, -38.43212237,
        -37.208413, -38.68068834, -39.80879541, -34.89483748
      ]
    }, {
      name: 'High-income economies',
      data: [0., -3.79916982, 2.56979075, 1.64046234,
        25.11785962, 28.48493551, 7.40972073, -3.22588365,
        -16.27539665, -23.56073659, -27.93183287, -29.36730859,
        -16.74025415, -17.90867973, -22.13996599, -14.17887142,
        20.30679398, 20.92943886, 28.33189748, 51.53755032,
        59.28569062, 57.03807404, 52.66828476, 42.157549,
        63.36043506, 53.23228516, 46.82263623, 57.9479448
      ]
    }, {
      name: 'Upper-middle-income economies',
      data: [0., 7.00681792, 9.13517055, 1.63870923,
        4.03211064, 15.45684128, 22.86420355, 23.29399657,
        16.32847887, 13.10977055, 5.64323387, 2.16859965,
        11.00007448, 18.74466821, 18.24785762, 33.51461418,
        59.52156074, 106.00951936, 82.87170355, 111.38103672,
        131.04692652, 118.6710014, 129.2297172, 128.91150245,
        129.03261024, 108.04365636, 115.11108983, 128.84463048
      ]
    }, {
      name: 'Lower-middle-income economies',
      data: [0., 4.321096, -1.49346979, 5.2778616,
        3.97051348, 8.58596376, 19.0361616, 9.23261833,
        7.13104014, 3.92729995, 5.23137797, 4.94657516,
        17.47633356, 24.3074949, 31.29047293, 31.09190812,
        64.78197919, 106.27501926, 104.66926928, 101.47733592,
        133.62961675, 135.11320025, 115.93374446, 77.77662082,
        61.62041647, 85.15715646, 56.31253781, 67.37274269
      ]
    }, {
      name: 'Low income economies',
      data: [0., -8.61511953, -18.16444109, -23.71550961,
        -4.22254214, -13.02079594, -13.60808808, -7.61480843,
        -23.67004092, -35.48711322, -35.39617584, -12.71296916,
        -11.64237682, 2.85591213, 22.48238516, 15.76297652,
        31.41858079, 76.624309, 50.23537737, 34.55470601,
        65.90297222, 70.8082059, 80.61905788, 57.87924474,
        69.99197227, 56.01366112, 30.72118491, -1.28987484
      ]
    }],

    responsive: {
      rules: [{
        condition: {
          maxWidth: 500
        },
        chartOptions: {
          legend: {
            layout: 'horizontal',
            align: 'center',
            verticalAlign: 'bottom'
          }
        }
      }]
    }

  });

  Highcharts.chart('co2_loss', {
    chart: {
      type: 'area'
    },
    title: {
      text: 'Agriculture Loss in CO2 Equivalence  '
    },

    xAxis: {
      categories: [
        1961, 1962, 1963, 1964, 1965, 1966, 1967, 1968, 1969, 1970, 1971,
        1972, 1973, 1974, 1975, 1976, 1977, 1978, 1979, 1980, 1981, 1982,
        1983, 1984, 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993,
        1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2002, 2003, 2004,
        2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013
      ],
      tickmarkPlacement: 'on',
      title: {
        enabled: false
      }
    },
    yAxis: {
      title: {
        text: '1000 tonnes'
      },

    },
    tooltip: {
      split: true,
      valueSuffix: 'k ',

    },
    plotOptions: {
      area: {
        stacking: 'normal',
        lineColor: '#666666',
        lineWidth: 1,
        marker: {
          enabled: false
        }
      }
    },
    series: [{
      name: 'Starchy Roots',
      data: [57.33, 36.78, 33.53, 21.63, 22.71, 43.27, 40.02, 23.8, 21.63,
        48.67, 51.92, 25.96, 42.18, 18.39, 19.47, 20.55, 16.22, 30.29,
        16.22, 32.45, 64.9, 38.94, 58.41, 71.39, 50.84, 27.04, 24.88,
        27.04, 27.04, 25.96, 17.31, 23.8, 22.71, 22.71, 22.71, 23.8,
        22.71, 22.71, 21.63, 21.63, 19.47, 21.63, 22.71, 24.88, 22.71,
        22.71, 23.8, 23.8, 27.04, 27.04, 30.29, 29.2, 28.12
      ]

    }, {
      name: 'Fruits',
      data: [13.26, 18.95, 13.26, 17.05, 16.1, 16.1, 18.95, 18.95, 17.05,
        18, 21.79, 19.89, 21.79, 23.68, 21.79, 22.74, 19.89, 23.68,
        26.53, 23.68, 24.63, 28.42, 27.47, 32.21, 30.31, 27.47, 26.53,
        33.16, 32.21, 29.37, 28.42, 31.26, 43.58, 36.95, 36.95, 36,
        36.95, 29.37, 32.21, 35.05, 35.05, 35.05, 35.05, 39.79, 44.52,
        69.15, 54.94, 58.73, 63.47, 60.63, 48.31, 75.79, 82.42
      ]
    }, {

      name: 'Vegetables',
      data: [40.81, 46.46, 42.69, 42.69, 42.07, 52.11, 47.09, 47.09, 57.13,
        46.46, 35.79, 55.25, 28.88, 39.55, 35.16, 28.25, 30.14, 26.37,
        25.11, 26.37, 21.97, 41.44, 21.35, 35.16, 23.23, 21.35, 40.81,
        37.67, 52.74, 50.86, 43.32, 51.48, 28.25, 40.18, 32.02, 35.16,
        23.86, 33.9, 36.41, 26.37, 21.97, 16.32, 16.32, 16.95, 16.32,
        16.95, 35.16, 20.09, 27.63, 12.56, 14.44, 13.18, 13.81
      ]
    }, {
      name: 'Cereals',
      data: [12.64, 11.55, 12.64, 12.37, 9.24, 10.74, 11.42, 11.15, 9.92,
        9.92, 11.15, 8.43, 9.24, 9.52, 9.24, 7.88, 7.2, 9.11,
        8.84, 8.7, 10.74, 9.79, 7.2, 9.38, 8.29, 7.61, 6.66,
        8.56, 7.88, 7.2, 6.8, 11.42, 11.69, 8.56, 8.56, 9.52,
        9.24, 7.61, 6.53, 8.16, 6.8, 7.07, 6.12, 6.8, 6.53,
        3.67, 4.35, 3.4, 3.67, 2.72, 4.35, 1.9, 2.04
      ]

    }]
  });

  Highcharts.chart('footprint', {
    chart: {
      type: 'variablepie'
    },
    title: {
      text: 'Swiss Food Carbon Footprint'
    },
    tooltip: {
      headerFormat: '',
      pointFormat: '<span style="color:{point.color}">\u25CF</span> <b> {point.name}</b><br/>' +
        'CO2 Emission: <b>{point.y}</b><br/>' + 'kg/capita/year'
    },
    series: [{
      minPointSize: 10,
      innerSize: '20%',
      zMin: 0,
      name: 'countries',
      allowPointSelect: true,
      data: [{
        name: 'Fruits',
        y: 78.08,
        z: 6
      }, {
        name: 'Cereals',
        y: 100.78,
        z: 4
      }, {
        name: 'Alcoholic Beverage',
        y: 188.78,
        z: 3
      }, {
        name: 'Meat',
        y: 783.3,
        z: 2
      }, {
        name: 'Starchy Roots',
        y: 6.73,
        z: 8
      }, {
        name: 'Milk & derivatives',
        y: 2463.75,
        z: 1
      }, {
        name: 'Vegetables',
        y: 97.47,
        z: 5
      }, {
        name: 'Sugar & Sweeteners',
        y: 23.66,
        z: 7
      }]
    }]
  });

  // Splice in transparent for the center circle

Highcharts.chart('sunburst', {

  title: {
    text: 'Switzerland Importations 2017'
  },

  subtitle: {
    text: 'Click on some part of the figure for more information'
  },

  series: [{
    type: "sunburst",
    data: [
    {
      id: "0",
      parent: "999",
      name: "Alcohol",
      value: 293899.0
    }, {
      id: "1",
      parent: "999",
      name: "Cereals",
      value: 1141459.0
    }, {
      id: "2",
      parent: "999",
      name: "Fruits",
      value: 537624.0
    }, {
      id: "3",
      parent: "999",
      name: "Meat",
      value: 86829.0
    }, {
      id: "4",
      parent: "999",
      name: "Milk",
      value: 107069.0
    }, {
      id: "5",
      parent: "999",
      name: "Starchy Roots",
      value: 57187.0
    }, {
      id: "6",
      parent: "999",
      name: "Sugar",
      value: 420544.0
    }, {
      id: "7",
      parent: "999",
      name: "Vegetables",
      value: 270081.0
    }, {
      id: "0.0",
      parent: "0",
      name: "Beer",
      value: 99820.0
    }, {
      id: "0.1",
      parent: "0",
      name: "Beverages, Alcoholic",
      value: 17233.0
    }, {
      id: "0.2",
      parent: "0",
      name: "Beverages, Fermented",
      value: 6817.0
    }, {
      id: "0.3",
      parent: "0",
      name: "Wine",
      value: 170029.0
    }, {
      id: "1.4",
      parent: "1",
      name: "Barley",
      value: 143872.0
    }, {
      id: "1.5",
      parent: "1",
      name: "Other",
      value: 9211.0
    }, {
      id: "1.6",
      parent: "1",
      name: "Maize",
      value: 191865.0
    }, {
      id: "1.7",
      parent: "1",
      name: "Millet",
      value: 1355.0
    }, {
      id: "1.8",
      parent: "1",
      name: "Oats",
      value: 51053.0
    }, {
      id: "1.9",
      parent: "1",
      name: "Rice (Milled Equivalent)",
      value: 106619.0
    }, {
      id: "1.10",
      parent: "1",
      name: "Rye",
      value: 2776.0
    }, {
      id: "1.11",
      parent: "1",
      name: "Sorghum",
      value: 164.0
    }, {
      id: "1.12",
      parent: "1",
      name: "Wheat",
      value: 634544.0
    }, {
      id: "2.13",
      parent: "2",
      name: "Apples",
      value: 13685.0
    }, {
      id: "2.14",
      parent: "2",
      name: "Bananas",
      value: 88434.0
    }, {
      id: "2.15",
      parent: "2",
      name: "Citrus, Other",
      value: 4257.0
    }, {
      id: "2.16",
      parent: "2",
      name: "Dates",
      value: 2545.0
    }, {
      id: "2.17",
      parent: "2",
      name: "Other",
      value: 190799.0
    }, {
      id: "2.18",
      parent: "2",
      name: "Grapefruit",
      value: 7775.0
    }, {
      id: "2.19",
      parent: "2",
      name: "Grapes",
      value: 42146.0
    }, {
      id: "2.20",
      parent: "2",
      name: "Lemons, Limes",
      value: 24848.0
    }, {
      id: "2.21",
      parent: "2",
      name: "Oranges, Mandarines",
      value: 135173.0
    }, {
      id: "2.22",
      parent: "2",
      name: "Pineapples",
      value: 26531.0
    }, {
      id: "2.23",
      parent: "2",
      name: "Plantains",
      value: 1431.0
    }, {
      id: "3.24",
      parent: "3",
      name: "Bovine Meat",
      value: 20500.0
    }, {
      id: "3.25",
      parent: "3",
      name: "Meat, Other",
      value: 4179.0
    }, {
      id: "3.26",
      parent: "3",
      name: "Mutton & Goat Meat",
      value: 6397.0
    }, {
      id: "3.27",
      parent: "3",
      name: "Pigmeat",
      value: 10079.0
    }, {
      id: "3.28",
      parent: "3",
      name: "Poultry Meat",
      value: 45674.0
    }, {
      id: "4.29",
      parent: "4",
      name: "Milk - Excluding Butter",
      value: 107069.0
    }, {
      id: "5.30",
      parent: "5",
      name: "Cassava",
      value: 1121.0
    }, {
      id: "5.31",
      parent: "5",
      name: "Potatoes",
      value: 52525.0
    }, {
      id: "5.32",
      parent: "5",
      name: "Roots, Other",
      value: 186.0
    }, {
      id: "5.33",
      parent: "5",
      name: "Sweet potatoes",
      value: 3355.0
    }, {
      id: "6.34",
      parent: "6",
      name: "Honey",
      value: 6791.0
    }, {
      id: "6.35",
      parent: "6",
      name: "Sugar (Raw Equivalent)",
      value: 97087.0
    }, {
      id: "6.36",
      parent: "6",
      name: "Sweeteners, Other",
      value: 316666.0
    }, {
      id: "7.37",
      parent: "7",
      name: "Onions",
      value: 3863.0
    }, {
      id: "7.38",
      parent: "7",
      name: "Tomatoes",
      value: 78308.0
    }, {
      id: "7.39",
      parent: "7",
      name: "Vegetables, Other",
      value: 187910.0
    }, {
      id: "0.0.0",
      parent: "0.0",
      name: "Germany",
      value: 49586.0
    }, {
      id: "0.0.1",
      parent: "0.0",
      name: "Portugal",
      value: 20359.0
    }, {
      id: "0.0.2",
      parent: "0.0",
      name: "Netherlands",
      value: 11319.0
    }, {
      id: "0.0.3",
      parent: "0.0",
      name: "France",
      value: 9872.0
    }, {
      id: "0.0.4",
      parent: "0.0",
      name: "Mexico",
      value: 5413.0
    }, {
      id: "0.0.5",
      parent: "0.0",
      name: "Italy",
      value: 3271.0
    }, {
      id: "0.1.6",
      parent: "0.1",
      name: "Italy",
      value: 5781.0
    }, {
      id: "0.1.7",
      parent: "0.1",
      name: "United Kingdom",
      value: 4014.0
    }, {
      id: "0.1.8",
      parent: "0.1",
      name: "Germany",
      value: 3550.0
    }, {
      id: "0.1.9",
      parent: "0.1",
      name: "France",
      value: 2052.0
    }, {
      id: "0.1.10",
      parent: "0.1",
      name: "United States of America",
      value: 1173.0
    }, {
      id: "0.1.11",
      parent: "0.1",
      name: "Ireland",
      value: 663.0
    }, {
      id: "0.2.12",
      parent: "0.2",
      name: "Germany",
      value: 4150.0
    }, {
      id: "0.2.13",
      parent: "0.2",
      name: "Belgium",
      value: 708.0
    }, {
      id: "0.2.14",
      parent: "0.2",
      name: "France",
      value: 696.0
    }, {
      id: "0.2.15",
      parent: "0.2",
      name: "Italy",
      value: 619.0
    }, {
      id: "0.2.16",
      parent: "0.2",
      name: "Ireland",
      value: 354.0
    }, {
      id: "0.2.17",
      parent: "0.2",
      name: "Austria",
      value: 290.0
    }, {
      id: "0.3.18",
      parent: "0.3",
      name: "Italy",
      value: 76649.0
    }, {
      id: "0.3.19",
      parent: "0.3",
      name: "France",
      value: 39632.0
    }, {
      id: "0.3.20",
      parent: "0.3",
      name: "Spain",
      value: 31445.0
    }, {
      id: "0.3.21",
      parent: "0.3",
      name: "Portugal",
      value: 10638.0
    }, {
      id: "0.3.22",
      parent: "0.3",
      name: "Germany",
      value: 7152.0
    }, {
      id: "0.3.23",
      parent: "0.3",
      name: "South Africa",
      value: 4513.0
    }, {
      id: "1.4.24",
      parent: "1.4",
      name: "Germany",
      value: 65947.0
    }, {
      id: "1.4.25",
      parent: "1.4",
      name: "France",
      value: 46399.0
    }, {
      id: "1.4.26",
      parent: "1.4",
      name: "Hungary",
      value: 15937.0
    }, {
      id: "1.4.27",
      parent: "1.4",
      name: "Czechia",
      value: 9819.0
    }, {
      id: "1.4.28",
      parent: "1.4",
      name: "Slovakia",
      value: 3346.0
    }, {
      id: "1.4.29",
      parent: "1.4",
      name: "Austria",
      value: 2424.0
    }, {
      id: "1.5.30",
      parent: "1.5",
      name: "Italy",
      value: 6100.0
    }, {
      id: "1.5.31",
      parent: "1.5",
      name: "Germany",
      value: 1342.0
    }, {
      id: "1.5.32",
      parent: "1.5",
      name: "Bolivia (Plurinational State of)",
      value: 708.0
    }, {
      id: "1.5.33",
      parent: "1.5",
      name: "France",
      value: 440.0
    }, {
      id: "1.5.34",
      parent: "1.5",
      name: "Austria",
      value: 343.0
    }, {
      id: "1.5.35",
      parent: "1.5",
      name: "China, mainland",
      value: 278.0
    }, {
      id: "1.6.36",
      parent: "1.6",
      name: "France",
      value: 73435.0
    }, {
      id: "1.6.37",
      parent: "1.6",
      name: "Germany",
      value: 46320.0
    }, {
      id: "1.6.38",
      parent: "1.6",
      name: "China, mainland",
      value: 32735.0
    }, {
      id: "1.6.39",
      parent: "1.6",
      name: "Romania",
      value: 17881.0
    }, {
      id: "1.6.40",
      parent: "1.6",
      name: "Hungary",
      value: 11491.0
    }, {
      id: "1.6.41",
      parent: "1.6",
      name: "Slovakia",
      value: 10003.0
    }, {
      id: "1.7.42",
      parent: "1.7",
      name: "Austria",
      value: 564.0
    }, {
      id: "1.7.43",
      parent: "1.7",
      name: "Hungary",
      value: 294.0
    }, {
      id: "1.7.44",
      parent: "1.7",
      name: "Germany",
      value: 261.0
    }, {
      id: "1.7.45",
      parent: "1.7",
      name: "France",
      value: 105.0
    }, {
      id: "1.7.46",
      parent: "1.7",
      name: "Ukraine",
      value: 89.0
    }, {
      id: "1.7.47",
      parent: "1.7",
      name: "Netherlands",
      value: 42.0
    }, {
      id: "1.8.48",
      parent: "1.8",
      name: "Finland",
      value: 20863.0
    }, {
      id: "1.8.49",
      parent: "1.8",
      name: "Germany",
      value: 15170.0
    }, {
      id: "1.8.50",
      parent: "1.8",
      name: "France",
      value: 6809.0
    }, {
      id: "1.8.51",
      parent: "1.8",
      name: "Czechia",
      value: 4233.0
    }, {
      id: "1.8.52",
      parent: "1.8",
      name: "Sweden",
      value: 2639.0
    }, {
      id: "1.8.53",
      parent: "1.8",
      name: "Austria",
      value: 1339.0
    }, {
      id: "1.9.54",
      parent: "1.9",
      name: "Brazil",
      value: 48721.0
    }, {
      id: "1.9.55",
      parent: "1.9",
      name: "Italy",
      value: 24678.0
    }, {
      id: "1.9.56",
      parent: "1.9",
      name: "Thailand",
      value: 14446.0
    }, {
      id: "1.9.57",
      parent: "1.9",
      name: "India",
      value: 7781.0
    }, {
      id: "1.9.58",
      parent: "1.9",
      name: "Russian Federation",
      value: 6842.0
    }, {
      id: "1.9.59",
      parent: "1.9",
      name: "Uruguay",
      value: 4151.0
    }, {
      id: "1.10.60",
      parent: "1.10",
      name: "Austria",
      value: 1203.0
    }, {
      id: "1.10.61",
      parent: "1.10",
      name: "Germany",
      value: 947.0
    }, {
      id: "1.10.62",
      parent: "1.10",
      name: "Ukraine",
      value: 330.0
    }, {
      id: "1.10.63",
      parent: "1.10",
      name: "Serbia",
      value: 182.0
    }, {
      id: "1.10.64",
      parent: "1.10",
      name: "United Kingdom",
      value: 62.0
    }, {
      id: "1.10.65",
      parent: "1.10",
      name: "Lithuania",
      value: 52.0
    }, {
      id: "1.11.66",
      parent: "1.11",
      name: "Italy",
      value: 102.0
    }, {
      id: "1.11.67",
      parent: "1.11",
      name: "France",
      value: 50.0
    }, {
      id: "1.11.68",
      parent: "1.11",
      name: "Russian Federation",
      value: 9.0
    }, {
      id: "1.11.69",
      parent: "1.11",
      name: "Argentina",
      value: 1.0
    }, {
      id: "1.11.70",
      parent: "1.11",
      name: "Austria",
      value: 1.0
    }, {
      id: "1.11.71",
      parent: "1.11",
      name: "Germany",
      value: 1.0
    }, {
      id: "1.12.72",
      parent: "1.12",
      name: "Germany",
      value: 240304.0
    }, {
      id: "1.12.73",
      parent: "1.12",
      name: "France",
      value: 141816.0
    }, {
      id: "1.12.74",
      parent: "1.12",
      name: "Austria",
      value: 80452.0
    }, {
      id: "1.12.75",
      parent: "1.12",
      name: "Canada",
      value: 60689.0
    }, {
      id: "1.12.76",
      parent: "1.12",
      name: "Italy",
      value: 60283.0
    }, {
      id: "1.12.77",
      parent: "1.12",
      name: "Hungary",
      value: 51000.0
    }, {
      id: "2.13.78",
      parent: "2.13",
      name: "Italy",
      value: 7178.0
    }, {
      id: "2.13.79",
      parent: "2.13",
      name: "Germany",
      value: 2506.0
    }, {
      id: "2.13.80",
      parent: "2.13",
      name: "New Zealand",
      value: 1630.0
    }, {
      id: "2.13.81",
      parent: "2.13",
      name: "France",
      value: 1078.0
    }, {
      id: "2.13.82",
      parent: "2.13",
      name: "Chile",
      value: 819.0
    }, {
      id: "2.13.83",
      parent: "2.13",
      name: "Belgium",
      value: 474.0
    }, {
      id: "2.14.84",
      parent: "2.14",
      name: "Colombia",
      value: 38634.0
    }, {
      id: "2.14.85",
      parent: "2.14",
      name: "Panama",
      value: 18585.0
    }, {
      id: "2.14.86",
      parent: "2.14",
      name: "Ecuador",
      value: 11576.0
    }, {
      id: "2.14.87",
      parent: "2.14",
      name: "Peru",
      value: 9287.0
    }, {
      id: "2.14.88",
      parent: "2.14",
      name: "Costa Rica",
      value: 5584.0
    }, {
      id: "2.14.89",
      parent: "2.14",
      name: "Dominican Republic",
      value: 4768.0
    }, {
      id: "2.15.90",
      parent: "2.15",
      name: "Italy",
      value: 3212.0
    }, {
      id: "2.15.91",
      parent: "2.15",
      name: "Argentina",
      value: 399.0
    }, {
      id: "2.15.92",
      parent: "2.15",
      name: "France",
      value: 268.0
    }, {
      id: "2.15.93",
      parent: "2.15",
      name: "Peru",
      value: 159.0
    }, {
      id: "2.15.94",
      parent: "2.15",
      name: "Brazil",
      value: 117.0
    }, {
      id: "2.15.95",
      parent: "2.15",
      name: "Uruguay",
      value: 102.0
    }, {
      id: "2.16.96",
      parent: "2.16",
      name: "Tunisia",
      value: 1280.0
    }, {
      id: "2.16.97",
      parent: "2.16",
      name: "Israel",
      value: 646.0
    }, {
      id: "2.16.98",
      parent: "2.16",
      name: "United States of America",
      value: 373.0
    }, {
      id: "2.16.99",
      parent: "2.16",
      name: "Netherlands",
      value: 108.0
    }, {
      id: "2.16.100",
      parent: "2.16",
      name: "Iran (Islamic Republic of)",
      value: 78.0
    }, {
      id: "2.16.101",
      parent: "2.16",
      name: "Algeria",
      value: 60.0
    }, {
      id: "2.17.102",
      parent: "2.17",
      name: "Spain",
      value: 86480.0
    }, {
      id: "2.17.103",
      parent: "2.17",
      name: "Italy",
      value: 50415.0
    }, {
      id: "2.17.104",
      parent: "2.17",
      name: "France",
      value: 23463.0
    }, {
      id: "2.17.105",
      parent: "2.17",
      name: "Germany",
      value: 11859.0
    }, {
      id: "2.17.106",
      parent: "2.17",
      name: "Peru",
      value: 9752.0
    }, {
      id: "2.17.107",
      parent: "2.17",
      name: "South Africa",
      value: 8830.0
    }, {
      id: "2.18.108",
      parent: "2.18",
      name: "South Africa",
      value: 1786.0
    }, {
      id: "2.18.109",
      parent: "2.18",
      name: "United States of America",
      value: 1726.0
    }, {
      id: "2.18.110",
      parent: "2.18",
      name: "Spain",
      value: 1546.0
    }, {
      id: "2.18.111",
      parent: "2.18",
      name: "Israel",
      value: 1400.0
    }, {
      id: "2.18.112",
      parent: "2.18",
      name: "France",
      value: 688.0
    }, {
      id: "2.18.113",
      parent: "2.18",
      name: "China, mainland",
      value: 629.0
    }, {
      id: "2.19.114",
      parent: "2.19",
      name: "Italy",
      value: 30709.0
    }, {
      id: "2.19.115",
      parent: "2.19",
      name: "France",
      value: 3258.0
    }, {
      id: "2.19.116",
      parent: "2.19",
      name: "South Africa",
      value: 2945.0
    }, {
      id: "2.19.117",
      parent: "2.19",
      name: "Turkey",
      value: 2767.0
    }, {
      id: "2.19.118",
      parent: "2.19",
      name: "India",
      value: 1664.0
    }, {
      id: "2.19.119",
      parent: "2.19",
      name: "Spain",
      value: 803.0
    }, {
      id: "2.20.120",
      parent: "2.20",
      name: "Spain",
      value: 16484.0
    }, {
      id: "2.20.121",
      parent: "2.20",
      name: "Brazil",
      value: 2568.0
    }, {
      id: "2.20.122",
      parent: "2.20",
      name: "Italy",
      value: 2523.0
    }, {
      id: "2.20.123",
      parent: "2.20",
      name: "South Africa",
      value: 1867.0
    }, {
      id: "2.20.124",
      parent: "2.20",
      name: "Mexico",
      value: 729.0
    }, {
      id: "2.20.125",
      parent: "2.20",
      name: "Argentina",
      value: 677.0
    }, {
      id: "2.21.126",
      parent: "2.21",
      name: "Spain",
      value: 80401.0
    }, {
      id: "2.21.127",
      parent: "2.21",
      name: "Italy",
      value: 20565.0
    }, {
      id: "2.21.128",
      parent: "2.21",
      name: "Brazil",
      value: 19026.0
    }, {
      id: "2.21.129",
      parent: "2.21",
      name: "South Africa",
      value: 7083.0
    }, {
      id: "2.21.130",
      parent: "2.21",
      name: "France",
      value: 5242.0
    }, {
      id: "2.21.131",
      parent: "2.21",
      name: "Israel",
      value: 2856.0
    }, {
      id: "2.22.132",
      parent: "2.22",
      name: "Costa Rica",
      value: 16590.0
    }, {
      id: "2.22.133",
      parent: "2.22",
      name: "Thailand",
      value: 4386.0
    }, {
      id: "2.22.134",
      parent: "2.22",
      name: "Ghana",
      value: 2215.0
    }, {
      id: "2.22.135",
      parent: "2.22",
      name: "Indonesia",
      value: 1760.0
    }, {
      id: "2.22.136",
      parent: "2.22",
      name: "Ecuador",
      value: 880.0
    }, {
      id: "2.22.137",
      parent: "2.22",
      name: "Panama",
      value: 700.0
    }, {
      id: "2.23.138",
      parent: "2.23",
      name: "Ecuador",
      value: 1202.0
    }, {
      id: "2.23.139",
      parent: "2.23",
      name: "Colombia",
      value: 165.0
    }, {
      id: "2.23.140",
      parent: "2.23",
      name: "Uganda",
      value: 47.0
    }, {
      id: "2.23.141",
      parent: "2.23",
      name: "Sri Lanka",
      value: 8.0
    }, {
      id: "2.23.142",
      parent: "2.23",
      name: "Spain",
      value: 5.0
    }, {
      id: "2.23.143",
      parent: "2.23",
      name: "Costa Rica",
      value: 4.0
    }, {
      id: "3.24.144",
      parent: "3.24",
      name: "Germany",
      value: 8613.0
    }, {
      id: "3.24.145",
      parent: "3.24",
      name: "Austria",
      value: 5104.0
    }, {
      id: "3.24.146",
      parent: "3.24",
      name: "Ireland",
      value: 3135.0
    }, {
      id: "3.24.147",
      parent: "3.24",
      name: "Paraguay",
      value: 1384.0
    }, {
      id: "3.24.148",
      parent: "3.24",
      name: "Uruguay",
      value: 1342.0
    }, {
      id: "3.24.149",
      parent: "3.24",
      name: "Australia",
      value: 922.0
    }, {
      id: "3.25.150",
      parent: "3.25",
      name: "Austria",
      value: 881.0
    }, {
      id: "3.25.151",
      parent: "3.25",
      name: "Hungary",
      value: 863.0
    }, {
      id: "3.25.152",
      parent: "3.25",
      name: "France",
      value: 685.0
    }, {
      id: "3.25.153",
      parent: "3.25",
      name: "New Zealand",
      value: 611.0
    }, {
      id: "3.25.154",
      parent: "3.25",
      name: "Belgium",
      value: 602.0
    }, {
      id: "3.25.155",
      parent: "3.25",
      name: "Argentina",
      value: 537.0
    }, {
      id: "3.26.156",
      parent: "3.26",
      name: "New Zealand",
      value: 2184.0
    }, {
      id: "3.26.157",
      parent: "3.26",
      name: "Australia",
      value: 2030.0
    }, {
      id: "3.26.158",
      parent: "3.26",
      name: "Ireland",
      value: 960.0
    }, {
      id: "3.26.159",
      parent: "3.26",
      name: "United Kingdom",
      value: 688.0
    }, {
      id: "3.26.160",
      parent: "3.26",
      name: "France",
      value: 451.0
    }, {
      id: "3.26.161",
      parent: "3.26",
      name: "Netherlands",
      value: 84.0
    }, {
      id: "3.27.162",
      parent: "3.27",
      name: "Italy",
      value: 5127.0
    }, {
      id: "3.27.163",
      parent: "3.27",
      name: "Germany",
      value: 2634.0
    }, {
      id: "3.27.164",
      parent: "3.27",
      name: "Austria",
      value: 766.0
    }, {
      id: "3.27.165",
      parent: "3.27",
      name: "Spain",
      value: 603.0
    }, {
      id: "3.27.166",
      parent: "3.27",
      name: "France",
      value: 506.0
    }, {
      id: "3.27.167",
      parent: "3.27",
      name: "Portugal",
      value: 443.0
    }, {
      id: "3.28.168",
      parent: "3.28",
      name: "Brazil",
      value: 18165.0
    }, {
      id: "3.28.169",
      parent: "3.28",
      name: "Germany",
      value: 9664.0
    }, {
      id: "3.28.170",
      parent: "3.28",
      name: "France",
      value: 7142.0
    }, {
      id: "3.28.171",
      parent: "3.28",
      name: "Hungary",
      value: 5598.0
    }, {
      id: "3.28.172",
      parent: "3.28",
      name: "Netherlands",
      value: 3124.0
    }, {
      id: "3.28.173",
      parent: "3.28",
      name: "Slovenia",
      value: 1981.0
    }, {
      id: "4.29.174",
      parent: "4.29",
      name: "France",
      value: 41556.0
    }, {
      id: "4.29.175",
      parent: "4.29",
      name: "Germany",
      value: 32123.0
    }, {
      id: "4.29.176",
      parent: "4.29",
      name: "Italy",
      value: 22029.0
    }, {
      id: "4.29.177",
      parent: "4.29",
      name: "Netherlands",
      value: 4576.0
    }, {
      id: "4.29.178",
      parent: "4.29",
      name: "Belgium",
      value: 4043.0
    }, {
      id: "4.29.179",
      parent: "4.29",
      name: "United States of America",
      value: 2742.0
    }, {
      id: "5.30.180",
      parent: "5.30",
      name: "Costa Rica",
      value: 534.0
    }, {
      id: "5.30.181",
      parent: "5.30",
      name: "Thailand",
      value: 269.0
    }, {
      id: "5.30.182",
      parent: "5.30",
      name: "Germany",
      value: 192.0
    }, {
      id: "5.30.183",
      parent: "5.30",
      name: "Ecuador",
      value: 52.0
    }, {
      id: "5.30.184",
      parent: "5.30",
      name: "Netherlands",
      value: 50.0
    }, {
      id: "5.30.185",
      parent: "5.30",
      name: "Pakistan",
      value: 24.0
    }, {
      id: "5.31.186",
      parent: "5.31",
      name: "Netherlands",
      value: 20282.0
    }, {
      id: "5.31.187",
      parent: "5.31",
      name: "Germany",
      value: 12852.0
    }, {
      id: "5.31.188",
      parent: "5.31",
      name: "France",
      value: 6903.0
    }, {
      id: "5.31.189",
      parent: "5.31",
      name: "Israel",
      value: 5026.0
    }, {
      id: "5.31.190",
      parent: "5.31",
      name: "Spain",
      value: 4013.0
    }, {
      id: "5.31.191",
      parent: "5.31",
      name: "Austria",
      value: 3449.0
    }, {
      id: "5.32.192",
      parent: "5.32",
      name: "Italy",
      value: 49.0
    }, {
      id: "5.32.193",
      parent: "5.32",
      name: "Ghana",
      value: 36.0
    }, {
      id: "5.32.194",
      parent: "5.32",
      name: "France",
      value: 31.0
    }, {
      id: "5.32.195",
      parent: "5.32",
      name: "Germany",
      value: 25.0
    }, {
      id: "5.32.196",
      parent: "5.32",
      name: "China, mainland",
      value: 24.0
    }, {
      id: "5.32.197",
      parent: "5.32",
      name: "Togo",
      value: 21.0
    }, {
      id: "5.33.198",
      parent: "5.33",
      name: "United States of America",
      value: 1813.0
    }, {
      id: "5.33.199",
      parent: "5.33",
      name: "Spain",
      value: 841.0
    }, {
      id: "5.33.200",
      parent: "5.33",
      name: "Honduras",
      value: 341.0
    }, {
      id: "5.33.201",
      parent: "5.33",
      name: "Egypt",
      value: 257.0
    }, {
      id: "5.33.202",
      parent: "5.33",
      name: "Senegal",
      value: 71.0
    }, {
      id: "5.33.203",
      parent: "5.33",
      name: "Uganda",
      value: 32.0
    }, {
      id: "6.34.204",
      parent: "6.34",
      name: "Mexico",
      value: 2211.0
    }, {
      id: "6.34.205",
      parent: "6.34",
      name: "Germany",
      value: 1857.0
    }, {
      id: "6.34.206",
      parent: "6.34",
      name: "Argentina",
      value: 1387.0
    }, {
      id: "6.34.207",
      parent: "6.34",
      name: "Austria",
      value: 557.0
    }, {
      id: "6.34.208",
      parent: "6.34",
      name: "Cuba",
      value: 484.0
    }, {
      id: "6.34.209",
      parent: "6.34",
      name: "France",
      value: 295.0
    }, {
      id: "6.35.210",
      parent: "6.35",
      name: "Czechia",
      value: 25844.0
    }, {
      id: "6.35.211",
      parent: "6.35",
      name: "Germany",
      value: 24961.0
    }, {
      id: "6.35.212",
      parent: "6.35",
      name: "France",
      value: 21054.0
    }, {
      id: "6.35.213",
      parent: "6.35",
      name: "Austria",
      value: 17845.0
    }, {
      id: "6.35.214",
      parent: "6.35",
      name: "Paraguay",
      value: 3929.0
    }, {
      id: "6.35.215",
      parent: "6.35",
      name: "Costa Rica",
      value: 3454.0
    }, {
      id: "6.36.216",
      parent: "6.36",
      name: "Italy",
      value: 90817.0
    }, {
      id: "6.36.217",
      parent: "6.36",
      name: "Germany",
      value: 77506.0
    }, {
      id: "6.36.218",
      parent: "6.36",
      name: "France",
      value: 63006.0
    }, {
      id: "6.36.219",
      parent: "6.36",
      name: "Austria",
      value: 52558.0
    }, {
      id: "6.36.220",
      parent: "6.36",
      name: "Netherlands",
      value: 16798.0
    }, {
      id: "6.36.221",
      parent: "6.36",
      name: "Czechia",
      value: 15981.0
    }, {
      id: "7.37.222",
      parent: "7.37",
      name: "France",
      value: 1462.0
    }, {
      id: "7.37.223",
      parent: "7.37",
      name: "Italy",
      value: 1074.0
    }, {
      id: "7.37.224",
      parent: "7.37",
      name: "Netherlands",
      value: 788.0
    }, {
      id: "7.37.225",
      parent: "7.37",
      name: "Spain",
      value: 280.0
    }, {
      id: "7.37.226",
      parent: "7.37",
      name: "New Zealand",
      value: 196.0
    }, {
      id: "7.37.227",
      parent: "7.37",
      name: "Egypt",
      value: 63.0
    }, {
      id: "7.38.228",
      parent: "7.38",
      name: "Italy",
      value: 46099.0
    }, {
      id: "7.38.229",
      parent: "7.38",
      name: "Spain",
      value: 18061.0
    }, {
      id: "7.38.230",
      parent: "7.38",
      name: "Morocco",
      value: 6033.0
    }, {
      id: "7.38.231",
      parent: "7.38",
      name: "Netherlands",
      value: 4010.0
    }, {
      id: "7.38.232",
      parent: "7.38",
      name: "Portugal",
      value: 2128.0
    }, {
      id: "7.38.233",
      parent: "7.38",
      name: "France",
      value: 1977.0
    }, {
      id: "7.39.234",
      parent: "7.39",
      name: "Spain",
      value: 91673.0
    }, {
      id: "7.39.235",
      parent: "7.39",
      name: "Italy",
      value: 43006.0
    }, {
      id: "7.39.236",
      parent: "7.39",
      name: "Netherlands",
      value: 18212.0
    }, {
      id: "7.39.237",
      parent: "7.39",
      name: "Germany",
      value: 14257.0
    }, {
      id: "7.39.238",
      parent: "7.39",
      name: "France",
      value: 11864.0
    }, {
      id: "7.39.239",
      parent: "7.39",
      name: "Turkey",
      value: 8898.0
    }],
    allowDrillToNode: true,
    cursor: 'pointer',

    levels: [{
        level: 1,
        colorByPoint: true,
        levelSize: {
          unit: 'percentage',
          value: 50
        }

      },
      {
        level: 2,
        levelSize: {
          unit: 'percentage',
          value: 35
        }


      }, {
        level: 3,
        levelSize: {
          unit: 'percentage',
          value: 15
        }

      }
    ]

  }],
  tooltip: {
    headerFormat: "",
    pointFormat: 'The amount of imports of <b>{point.name}</b> is <b>{point.value}</b> tonnes'
  }
});

</script>
