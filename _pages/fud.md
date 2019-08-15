---
permalink: /fud/
title: "Bitcoin FUD"

header:
  teaser: /assets/images/covers/CY19M7-cover-1000-glitch.gif
  overlay_image: /assets/images/covers/CY19M7-cover-header-glitch.gif
  overlay_filter: 0.50
  actions:
    - label: "How to deal with Bitcoin FUD - insert cheatsheet download here"
      url: "/assets/publications/CY19M7.pdf"

defaults:
  - scope:
      type: pages
    values:
      author_profile: true
---

# How to use this page
This page is intended to be a place you can reference when you encounter FUD online and IRL. H/T to [Inner-Smile](https://www.inner-smile.com/bitcoin-fud.phtml)

# Bitcoin is controlled by miners


# Bitcoin is too slow

# Bitcoin is too expensive

# Bitcoin is bad for the environment

Bitcoin energy usage is all about utilizing the most cost efficient energy, this means using renewables at near zero cost or even capturing energy that would otherwise be wasted, like natural gas flaring.

Yes, it's true that Bitcoin uses energy just like every other money and human activity. A key difference is that Bitcoin uses energy to secure the hardest money mankind has ever known. 

When someone says it is wasteful, they are placing themselves on a morally superior pedistal by trying to tell you what's the best way to use energy. There's nothing immoral about using energy to run Bitcoin.

# Bitcoin is a waste

> "Gold mining is a waste, but that waste is far less than the utility of having gold available as a medium of exchange. I think the case will be the same for Bitcoin." - Satoshi

# Bitcoin is centralized by Core devs

# Bitcoin has no intrinsic value
We believe Bitcoin having no intrinsic value is a good thing. 

# Bitcoin doesn't scale

# Bitcoin is too volatile

# Bitcoin is for criminals

# Bitcoin is centralized, look at Satoshi's wallet

# Bitcoin isn't money

# Bitcoin gets hacked, look at Mt. Gox

# Bitcoin is deflationary and that's terrible

# Bitcoin will get banned and/or regulated to death

# Bitcoin transactions aren't private

# Bitcoin supply cap is a flaw

# Bitcoin distribution isn't fair

[Bitcoin’s Distribution was Fair](https://www.danheld.com/blog/2019/1/6/bitcoins-distribution-was-fair)

# Test Area for Charts

<iframe class="highcharts-iframe" src="https://cloud.highcharts.com/embed/anDcC1rSH/" style="border: 0; width: 100%; height: 500px"></iframe>


<div class="container">
        <canvas id="myChart"></canvas>
</div>
<script>
        let myChart = document.getElementById('myChart').getContext('2d');
        
        // Global Option
        Chart.defaults.global.defaultFontFamily = 'Raleway';
        Chart.defaults.global.defaultFontWeight = 400;
        Chart.defaults.global.defaultFontSize = 18;
        Chart.defaults.global.defaultFontFontColor = '#777';

        let USInflationRateForJanuary = new Chart(myChart, {
            type:'polarArea',
            data:{
                labels:['2019', '2018', '2017', '2016', '2015'],
                datasets:[{
                    label:'Past 5 Years January Inflation Rate',
                    data:[
                        1.6,
                        2.1,
                        2.5,
                        1.4,
                        -0.1
                    ],
                    //backgroundColor: 'green'
                    backgroundColor:[
                        '#474747',
                        '#636468',
                        '#939598',
                        '#C6C8CA',
                        '#CC0000'
                    ],
                    borderWidth:4,
                    borderColor:'#777',
                    hoverBorderWidth:2,
                    hoverBorderColor:'000'

                }]
            },
            options:{
                title:{
                    display:true,
                    text:'US Inflation Rates',
                    fontSize: 40,
                },
                legend:{
                    display:true,
                    position:'right',
                    labels:{
                        fontColor:'black'
                    }
                },
                layout:{
                    padding:{
                        left:50,
                        right:0,
                        bottom:0,
                        top:50
                    }
                },
                tooltips:{
                    enabled:true,
                },
            }
        })
</script>