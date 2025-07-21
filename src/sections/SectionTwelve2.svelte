<script>
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleFadeIn from "../lib/ObservedArticleFadeIn.svelte";

  let options = {
    chart: {
      type: "line",
      backgroundColor: "black",
    },
    title: {
      text: "Median Annual Earnings by Race (Bachelor’s or Higher, 2010–2022)",
      style: { color: "white" },
    },
    subtitle: {
      text: "Full-Time Workers (25-34 Years Old)",
      style: { color: "white" },
    },
    xAxis: {
      categories: [
        2010, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022,
      ],
      labels: { style: { color: "white" } },
    },
    yAxis: {
      title: {
        text: "Median Earnings (USD)",
        style: { color: "white" },
      },
      labels: {
        formatter: function () {
          return "$" + this.value.toLocaleString();
        },
        style: { color: "white" },
      },
      gridLineColor: "#444",
    },
    tooltip: {
      shared: true,
      backgroundColor: "#222",
      style: { color: "white" },
      valuePrefix: "$",
    },
    legend: {
      itemStyle: { color: "white" },
    },
    plotOptions: {
      series: {
        marker: {
          enabled: false,
        },
      },
    },
    series: [
      {
        name: "Asian",
        data: [
          80910, 83250, 77410, 76720, 86700, 85580, 84860, 83750, 85150, 87540,
          92590, 91130,
        ],
        color: "#f27d16",
      },
      {
        name: "White",
        data: [
          67380, 64900, 65000, 65310, 67980, 67760, 68250, 70450, 70660, 72490,
          72620, 71650,
        ],
        color: "#e0dcd5",
      },
      {
        name: "Hispanic",
        data: [
          60220, 58490, 58780, 59940, 63810, 61530, 58700, 59230, 58320, 60540,
          61290, 60200,
        ],
        color: "#ffcc00",
      },
      {
        name: "Black",
        data: [
          56120, 57490, 57420, 58780, 59180, 62000, 55870, 53940, 55060, 58790,
          60140, 61150,
        ],
        color: "#eb5e28",
      },
    ],
    credits: { enabled: false },
  };
</script>

<div>
  <Scroller layout="right">
    {#snippet sticky()}
      <h1>The Cost of Underrepresentation</h1>
      <h2>The Economic Toll When Connection Means Disconnection</h2>
      <div class="chart">
        <Chart {options} highcharts={Highcharts} />
      </div>
      <div class="text">
        <div class="reference">
          <a href="https://blackwealthdata.org/explore/education#EMP-01"
            ><small
              >The Black Wealth Data Center. (2025). Explore Data - Education.
              “Median Annual Earnings for Full-Time Workers (25-34 Years Old) by
              Race/Ethnicity (Nationwide, 2010 - 2022)”. Blackwealthdata.org.</small
            ></a
          >
        </div>
        <p>
          Asian degree-holders have consistently led in median income since
          2010. Their earnings trajectory climbs sharply over the decade,
          <strong
            >reflecting higher representation in lucrative STEM fields and
            stronger digital pipelines.</strong
          >
          White graduates earn significantly more than their Black and Hispanic peers.
          In 2022, White degree-holders earned over $71,000, while Black degree-holders
          earned just over $61,000,
          <strong>a $10,000 gap for the same education level.</strong> Despite having
          similar qualifications, Black graduates earn far less year after year.
          The climb is flatter and more fragile, impacted by barriers in tech job
          access, occupational segregation, and digital skill gaps.
        </p>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleFadeIn>
        In 2021, full-time STEM workers <strong
          >earned $19,100 more annually than non-STEM workers.</strong
        >
        Even among those without college degrees,
        <strong>STEM middle-skill jobs offered $10,000 more,</strong>
        showing opportunity across all levels. Yet as we know, Black Americans only
        hold 7.4% of digital roles. This underrepresentation narrows access to income
        and compounds generational wealth gaps.
        <span
          ><a href="https://ncses.nsf.gov/pubs/nsb20212"
            >National Center for Science and Engineering Statistics, "The STEM
            Labor Force of Today: Scientists, Engineers, and Skilled Technical
            Workers," August 2021.</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        The digital economy is also booming, but not equally. By 2030, <strong
          >tech and IT jobs are projected to grow 1.7× faster</strong
        >
        than other fields. These roles are not only multiplying, they’re some of
        the best-paid jobs in the market.
        <strong
          >Yet without intervention, the communities most disconnected risk
          falling even further behind.</strong
        >
        <span>
          <a
            href="https://www.bls.gov/news.release/archives/ecopro_09082021.pdf"
            >US Bureau of Labor Statistics, “Employment projections 2020–2030,”
            September 2021.</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        In 2022, the median net worth of Black households was just <strong
          >$44,100, compared to $248,310
        </strong>
        for White households. STEM jobs represent a chance to bridge these divides.
        But without targeted investment in digital access, training, and representation,
        the tech economy may deepen inequality rather than disrupt it.
        <span>
          <a href=" https://blackwealthdata.org/explore/assets"
            >The Black Wealth Data Center. (2022). Explore Data - Assets & Debt.
            “Median Total Net Worth for Households, by Race/Ethnicity
            (Nationwide, 2007-2022)”. Blackwealthdata.org.</a
          >
        </span>
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
  }

  h2 {
    font-family: "Raleway";
    font-weight: 500;
    font-style: normal;
    font-size: 25px;
    margin-top: 0;
    color: white;
  }

  small {
    color: rgb(173, 172, 172);
    text-align: left;
  }
  .reference {
    padding-left: 1rem;
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
