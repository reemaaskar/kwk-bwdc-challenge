<script>
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";

  import ObservedArticleFadeIn from "../lib/ObservedArticleFadeIn.svelte";

  let options = {
    chart: {
      type: "column",
      backgroundColor: "rgba(0,0,0,0.8)",
    },
    title: {
      text: "Broadband Access by Race (Selected Counties)",
      style: {
        color: "white",
        fontSize: "24px",
      },
    },
    xAxis: {
      categories: [
        "Issaquena, MS",
        "Washington, MS",
        "Sharkey, MS",
        "Leflore, MS",
        "Greene, AL",
        "Humphreys, MS",
        "Lowndes, AL",
        "East Carroll, LA",
        "Madison, LA",
        "Hancock, GA",
      ],
      title: {
        text: "County",
        style: { color: "white" },
      },
      labels: {
        style: {
          color: "white",
        },
      },
    },
    yAxis: {
      min: 0,
      max: 100,
      title: {
        text: "% Households with Broadband",
        style: {
          color: "white",
        },
      },
      labels: {
        style: {
          color: "white",
        },
      },
      gridLineColor: "#444",
    },
    legend: {
      itemStyle: {
        color: "white",
      },
    },
    tooltip: {
      shared: true,
      backgroundColor: "#222",
      style: {
        color: "white",
      },
    },
    series: [
      {
        type: "column",
        name: "Black Alone",
        data: [48.7, 54.8, 56.4, 57.6, 58.5, 63.0, 63.6, 64.9, 67.1, 67.5],
        color: "#eb5e28",
      },
      {
        type: "column",
        name: "White Alone",
        data: [60.5, 72.2, 64.7, 78.1, 88.6, 90.4, 82.1, 77.7, 78.9, 81.7],
        color: "#e0dcd5",
      },
    ],
    credits: {
      enabled: false,
    },
  };
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <h1>Offline and Overlooked</h1>
      <div class="chart">
        <Chart {options} highcharts={Highcharts} />
      </div>
      <div class="text">
        <div class="reference">
          <a href="https://blackwealthdata.org/explore/education#EDU-05"
            ><small
              >The Black Wealth Data Center. (2025). Explore Data - Education.
              “Percent Broadband Internet Subscription by Households, by
              Race/Ethnicity (Countywide, 2023)”. Blackwealthdata.org.</small
            ></a
          >
        </div>
        <p>
          Across these ten counties in the Deep South - from Issaquena,
          Mississippi to Hancock, Georgia - <strong
            >White households consistently report higher broadband access than
            their Black neighbours.</strong
          >
          In places like Leflore County, Mississippi, the divide stretches over
          <strong>20 percentage points, </strong> despite Black residents making
          up the majority. These counties weren’t chosen at random, they reflect
          where both
          <strong
            >Black population density is high and digital access is
            disproportionately low</strong
          >, drawing a direct line between race and connectivity on the map.
        </p>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleFadeIn>
        Even in 2025, <strong
          >internet access remains a racial equity issue.</strong
        >
        What was once seen as a luxury is now a basic requirement for education,
        work, and participation in modern life, yet too many Black families remain
        disconnected. The <strong>“digital divide”</strong>, first identified in
        the 1990s, still casts a long shadow, stalling progress in closing
        economic, educational, and opportunity gaps.
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        These gaps persist across both urban and rural landscapes. In cities
        like Chicago and Baltimore,
        <strong
          >Black residents are twice as likely to lack a broadband subscription</strong
        >
        compared to White residents. This urban connectivity crisis often mirrors
        redlining maps and reflects a long history of disinvestment in Black neighborhoods.
        <span
          ><a href="https://www.census.gov/programs-surveys/acs/data.html"
            >U.S. Census Bureau. (2020). American Community Survey, Five-Year
            Microdata Estimates</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        In the rural South, where infrastructure investment lags, the divide
        deepens. Nearly <strong>38% of Black households</strong> still don’t
        have internet access, compared to
        <strong>23% of White households</strong>.
        <span
          ><a
            href="https://jointcenter.org/affordability-availability-expanding-broadband-in-the-black-rural-south/"
            >Dominique Harrison, "Affordability & availability: Expanding
            broadband in the Black rural South, Joint Center for Political and
            Economic Studies," October 2021.</a
          > The “Black rural South” itself is a term used to describe more than 150
          rural counties with populations that are at least 35% Black.
        </span>
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        Nationally, <strong>around 40% of Black households</strong> lack
        high-speed broadband, compared to
        <strong>28% of White households</strong>. This is more than a
        connectivity issue, it’s a systemic access gap that limits students’
        ability to learn online, workers’ ability to apply for jobs, and
        families’ ability to access essential services.
        <span
          ><a href="https://www.census.gov/programs-surveys/acs/data.html"
            >U.S. Census Bureau. (2020). American Community Survey, Five-Year
            Microdata Estimates</a
          ></span
        >
      </ObservedArticleFadeIn>
    {/snippet}
  </Scroller>
</div>

<style>
  .chart {
    width: 100%;
    margin: 0px auto;
  }

  .text p {
    color: white;
    text-align: left;
    margin: 2vh;
  }

  .text strong {
    color: #eb5e28;
  }

  h1 {
    font-family: "Cal Sans", sans-serif;
    font-weight: 400;
    font-style: normal;
    font-size: 50px;
    margin-bottom: 0.7rem;
    color: white;
    margin-top: -10vh;
  }

  small {
    color: rgb(173, 172, 172);
    text-align: left;
  }
  .reference {
    margin-left: 1vw;
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
</style>
