<script>
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleFadeIn from "../lib/ObservedArticleFadeIn.svelte";

  const options = {
    chart: {
      type: "column",
      backgroundColor: "black",
      style: {
        fontFamily: "Raleway",
      },
    },
    title: {
      text: "Bridging the Digital Skills Divide",
      style: {
        color: "white",
        fontSize: "20px",
      },
    },
    xAxis: {
      categories: ["Digital Skills", "Computer Ownership"],
      crosshair: true,
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
        text: "Percentage (%)",
        style: { color: "white" },
      },
      labels: {
        style: { color: "white" },
      },
      gridLineColor: "#444",
    },
    legend: {
      itemStyle: { color: "white" },
    },
    tooltip: {
      shared: true,
      backgroundColor: "#222",
      borderColor: "#eb5e38",
      style: {
        color: "white",
      },
      valueSuffix: "%",
    },
    plotOptions: {
      column: {
        pointPadding: 0.2,
        borderWidth: 0,
      },
    },
    series: [
      {
        name: "Black Adults",
        data: [50, 69],
        color: "#eb5e28",
      },
      {
        name: "White Adults",
        data: [77, 80],
        color: "#e0dcd5",
      },
    ],
    credits: {
      enabled: false,
    },
  };
</script>

<div>
  <Scroller layout="left">
    {#snippet sticky()}
      <h1>Access Isn't Enough</h1>
      <h2>The Skills Gap That’s Holding Back Potential</h2>
      <div class="chart">
        <Chart {options} highcharts={Highcharts} />
      </div>
      <div class="text">
        <div class="reference">
          <a
            href="https://nationalskillscoalition.org/resource/publications/applying-a-racial-equity-lens-to-digital-literacy/"
            ><small>
              National Skills Coalition, "Applying a racial equity lens to digital
              literacy: How workers of color are affected by digital skill gaps," April
              2020
            </small></a
          >
          <br />
          <br />
          <a
            href="https://www.pewresearch.org/short-reads/2021/07/16/home-broadband-adoption-computer-ownership-vary-by-race-ethnicity-in-the-u-s/"
            ><small>
              Pew Research Center, "Home broadband adoption, computer ownership
              vary by race, ethnicity in the U.S.," April 2021
            </small></a
          >
        </div>
        <p></p>
        <p>
          Device ownership may be rising, but true digital access remains
          uneven. <strong>In many Black households, a computer is still out of
          reach,</strong>making everyday tasks like homework, job applications, or
          virtual appointments harder to complete. And even when devices are
          available, <strong>knowing how to use them effectively is another barrier.</strong> Far
          too often, Black adults are navigating a digital world without the
          same level of fluency or support systems others take for granted.
          These aren’t just technical challenges, they’re structural ones that
          quietly shape who gets to participate fully in today’s economy and who
          gets left behind.
        </p>
      </div>
    {/snippet}

    {#snippet scrolly()}

    <ObservedArticleFadeIn>
        Access to broadband is just the beginning. Without meaningful investment
        in digital literacy and support systems, connectivity alone cannot close
        the opportunity gap. <strong
          >True inclusion means ensuring Black communities not only get online,
          but thrive once they are.</strong
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        A 2020 OECD survey revealed just how wide the digital skills gap
        remains: <strong
          >only about half of Black adults in the U.S. were classified as having
          advanced or proficient digital abilities</strong
        >
        - the level often required to succeed in modern jobs or training programs.
        In contrast,
        <strong>77% of White adults were found to possess those skills</strong>,
        creating a 27-point divide that speaks not to individual shortcomings,
        but to systemic inequalities in digital education and access.
        <span
          ><a
            href="https://nationalskillscoalition.org/resource/publications/applying-a-racial-equity-lens-to-digital-literacy/"
          >
            National Skills Coalition, "Applying a racial equity lens to digital
            literacy: How workers of color are affected by digital skill gaps," April
            2020.</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        Lower levels of digital readiness are both a consequence and a
        compounding force behind the underrepresentation of Black Americans in
        the digital economy.
        <strong
          >While Black Americans make up approximately 13% of the U.S.
          workforce, they hold only 7.4% of digital jobs</strong
        >
        a striking disparity in one of the fastest-growing and highest-paying sectors.
        This lack of representation perpetuates income and opportunity gaps, making
        it harder for Black workers to break into the industries that increasingly
        define upward mobility.
        <span
          ><a href="https://www.bls.gov/opub/reports/race-and-ethnicity/2023/">
            US Bureau of Labor Statistics, "Labor force characteristics by race
            and ethnicity," 2021
          </a></span
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
    color: white;
    text-align: right;
    margin-right: -7vw;
    margin-bottom: 0.7rem;
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
    text-align: center;
  }
  .reference {
    text-align: right;
    padding-left: 3vw;
    padding-right: 3vw;
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
