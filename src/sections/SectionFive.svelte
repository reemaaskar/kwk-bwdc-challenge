<script>
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleFadeIn from "../lib/ObservedArticleFadeIn.svelte";
  const options = {
    chart: {
      type: "scatter",
      zoomType: "xy",
      backgroundColor: "black",
    },
    title: {
      text: "Black Population % vs High Speed Broadband Usage",
      style: { color: "white" },
    },
    subtitle: {
      text: "A Mississippi State Case Study",
      style: { color: "white" },
    },
    xAxis: {
      title: { text: "% Black Alone", style: { color: "white" } },
      labels: { style: { color: "white" } },
      gridLineColor: "#333",
    },
    yAxis: {
      title: {
        text: "% Broadband Usage (≥25 Mbps)",
        style: { color: "white" },
      },
      labels: { style: { color: "white" } },
      min: 0,
      max: 100,
      gridLineColor: "#333",
    },
    legend: { enabled: false },
    tooltip: {
      pointFormat:
        "<b>{point.name}</b><br>% Black: {point.x}<br>% Broadband: {point.y}",
    },
    series: [
      {
        name: "Counties",
        color: "#eb5e28",
        data: [
          { name: "Claiborne County", x: 86.2, y: 13.1 },
          { name: "Holmes County", x: 82.4, y: 7.0 },
          { name: "Jefferson County", x: 81.2, y: 5.3 },
          { name: "Tunica County", x: 79.6, y: 13.1 },
          { name: "Humphreys County", x: 78.8, y: 14.9 },
          { name: "Coahoma County", x: 75.9, y: 22.0 },
          { name: "Noxubee County", x: 73.8, y: 2.6 },
          { name: "Sharkey County", x: 73.7, y: 8.3 },
          { name: "Sunflower County", x: 73.0, y: 14.9 },
          { name: "Quitman County", x: 72.2, y: 5.3 },
          { name: "Issaquena County", x: 70.1, y: 14.5 },
          { name: "Wilkinson County", x: 67.2, y: 9.1 },
          { name: "Tallahatchie County", x: 62.1, y: 7.4 },
          { name: "Kemper County", x: 60.4, y: 2.7 },
          { name: "Jefferson Davis County", x: 60.2, y: 3.1 },
          { name: "Clay County", x: 60.1, y: 16.0 },
          { name: "Yazoo County", x: 58.1, y: 15.0 },
          { name: "Pike County", x: 54.1, y: 22.1 },
          { name: "Jasper County", x: 53.2, y: 14.7 },
          { name: "Copiah County", x: 50.7, y: 7.3 },
        ],
      },
      {
        name: "Trend Line",
        type: "line",
        color: "#e0dcd5",
        marker: { enabled: false },
        enableMouseTracking: false,
        data: [
          [50, -0.5907 * 50 + 65.23],
          [90, -0.5907 * 90 + 65.23],
        ],
      },
    ],
    credits: { enabled: false },
  };
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
      <h1>Price, Speed, and the Geography of Digital Inequality</h1>
      <div class="chart">
        <Chart {options} highcharts={Highcharts} />
      </div>
      <div class="text">
        <div class="reference">
          <a href="https://blackwealthdata.org/explore/education#EDU-09"
            ><small
              >The Black Wealth Data Center. (2025). Explore Data - Education.
              “High-Speed Broadband Internet Usage (25MBPS or higher)
              (Countywide, 2020)”. Blackwealthdata.org.</small
            ></a
          >
        </div>
        <p>
          In Mississippi, one of the states with the highest share of Black
          residents, broadband usage is among the lowest in the nation. BWDC’s
          analysis of Microsoft data shows that
          <strong
            >counties where 70% or more of the population is Black
            consistently fall into the bottom quartile for broadband usage
            nationwide.
          </strong> This is no accident. It’s the legacy of historic underinvestment
          in Black communities, especially in the rural South, where public infrastructure
          was never equitably distributed. These digital divides are tied to the
          same geographic and racial lines that once marked redlining, school segregation,
          and voting suppression.
        </p>

        <p></p>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleFadeIn>
        In dozens of U.S. cities, internet providers are offering dramatically
        slower speeds for the same price in Black and brown neighbourhoods. In
        New Orleans, one predominantly Black neighbourhood was offered just <strong
          >1 Mbps of service, barely enough to load a webpage, for $55 a month.
          Just blocks away, a mostly White area was offered 400 times faster
          speeds for the exact same price.</strong
        >
        These aren’t isolated glitches in the system. They are symptoms of a broader,
        systemic issue that has come to be known as
        <strong>digital redlining</strong>
        - a modern form of exclusion that denies equitable access to essential infrastructure.
        <span
          ><a
            href="https://www.pbs.org/newshour/economy/investigation-finds-lower-internet-speeds-for-higher-prices-in-poor-less-white-u-s-neighborhoods"
            >Yin, L., & Sankin, A. (2019). "Investigation finds lower internet
            speeds for higher prices in poor, less white U.S. neighborhoods," Accesed through PBS News</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        National maps may show broadband “coverage,” but in many places, what’s
        on offer is not usable internet. Microsoft estimates show that in <strong
          >Jefferson County, Mississippi, where more than 81% of
          residents are Black, only 5.3% of households are actually
          accessing high speed broadband. That's 15 times lower than the
          national average.</strong
        >
        What’s more alarming: this isn’t because people don’t want internet, it’s
        because the service available is too expensive, too slow, or both.
        <span
          ><a
            href="https://github.com/microsoft/USBroadbandUsagePercentages.git"
            >Microsoft High-Speed Broadband Usage, October 2020</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        A 2022 investigation by The Markup found that <strong
          >in two-thirds of the 38 cities studied, the worst internet deals,
          slow speeds, high prices, were disproportionately found in less-white,
          lower-income neighbourhoods.</strong
        >
        This is more than a coincidence. It’s a business model. And without transparency,
        regulation, and public pressure, the same inequities will continue to be
        baked into the next generation of digital infrastructure.
        <span
          ><a
            href="https://www.msnbc.com/opinion/msnbc-opinion/internet-prices-black-poor-neighborhoods-aren-t-fair-n1300137"
            >MSNBC, "Lower income neighborhoods shouldn't be paying so much for
            slower internet service," October 2022</a
          ></span
        >
      </ObservedArticleFadeIn>
    {/snippet}
  </Scroller>
</div>

<style>
  .chart {
    width: 90%;
    margin: 0px auto;
  }

  h1 {
    font-family: "Cal Sans", sans-serif;
    font-weight: 400;
    font-style: normal;
    font-size: 50px;
    margin-bottom: 1 rem;
    color: white;
    text-align: right;
    margin-right: 3vw;
  }

  small {
    color: rgb(173, 172, 172);
  }
  .reference {
    padding-right: 2rem;
    padding-left: 3rem;
    text-align: right;
  }

  a {
    text-decoration: none;
    color: rgb(143, 142, 142);
  }

  a:hover {
    color: #eb5e28;
    text-decoration: underline;
  }

  small:hover {
    color: #eb5e28;
    text-decoration: underline;
  }

  span {
    color: rgb(143, 142, 142);
    text-align: center;
    font-size: 14px;
  }

  .text p {
    color: white;
    text-align: right;
    margin: 5vh;
  }

  .text strong {
    color: #eb5e28;
  }
</style>
