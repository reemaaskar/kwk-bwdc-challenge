<script>
  import * as Highcharts from "highcharts";
  import "highcharts/modules/exporting";
  import { Chart } from "@highcharts/svelte";
  import Scroller from "../lib/Scroller.svelte";
  import ObservedArticleFadeIn from "../lib/ObservedArticleFadeIn.svelte";

  let options = {
    chart: {
      type: "bar",
      backgroundColor: "black",
    },
    title: {
      text: "STEM vs Non-STEM Degrees by Race and Gender (2021)",
      style: {
        color: "white",
      },
    },
    xAxis: {
      categories: [
        "Asian Males",
        "Asian Females",
        "", // spacer
        "Black Males",
        "Black Females",
        "", // spacer
        "Hispanic Males",
        "Hispanic Females",
        "", // spacer
        "White Males",
        "White Females",
      ],
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
        text: "Percentage of Degrees",
        style: {
          color: "white",
        },
      },
      labels: {
        format: "{value}%",
        style: {
          color: "white",
        },
      },
      reversedStacks: true,
    },
    legend: {
      itemStyle: {
        color: "white",
      },
    },
    plotOptions: {
      series: {
        stacking: "normal",
      },
    },
    tooltip: {
      pointFormat:
        '<span style="color:{series.color}">{series.name}</span>: <b>{point.y}%</b><br/>',
      shared: true,
      backgroundColor: "#333",
      style: {
        color: "white",
      },
    },
    series: [
      {
        name: "Non-STEM",
        color: "#e0dcd5",
        data: [
          37.2,
          51.8,
          null,
          58.5,
          79.3,
          null,
          53.6,
          73.6,
          null,
          48.8,
          71.2,
        ],
      },
      {
        name: "STEM",
        color: "#eb5e28",
        data: [
          62.8,
          48.2,
          null,
          41.5,
          20.7,
          null,
          46.4,
          26.4,
          null,
          51.2,
          28.8,
        ],
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
      <h1>Degrees of Disparity</h1>
      <h2>The Uneven Road Into STEM for Black Communities</h2>
      <div class="chart">
        <Chart {options} highcharts={Highcharts} />
      </div>
      <div class="text">
        <div class="reference">
          <a href="https://blackwealthdata.org/explore/education#EDU-05"
            ><small
              >The Black Wealth Data Center. (2025). Explore Data - Education.
              “STEM vs. non-STEM Employment Rates Among 25-34 Year Olds with a
              STEM Degree (Nationwide, 2021)”. Blackwealthdata.org.
            </small></a
          >
        </div>
        <p>
          In 2021, the paths into STEM looked very different depending on your
          race and gender. On one end, <strong
            >Asian men and women clustered toward STEM fields,</strong
          > with more than half of their degrees tied to science, technology,
          engineering, or math.
        </p>
        <p>
          On the other hand, the contrast isn’t subtle. For <strong
            >every 10 degrees earned by Black women, only 2 were in STEM.</strong
          > For <strong>Black men, it's closer to 4 out of 10,</strong> still
          below every other group. These aren't gaps, they’re signals of unequal
          pipelines, uneven preparation, and missed opportunity.
        </p>
        <p>
          While interest and talent stretch across all communities, access does
          not. This chart visualises the cost of that imbalance, one graduation
          at a time.
        </p>
      </div>
    {/snippet}

    {#snippet scrolly()}
      <ObservedArticleFadeIn>
        Despite decades of national attention on diversifying STEM, Black
        students remain significantly underrepresented across all levels of STEM
        degrees. In 2018, <strong
          >Black students earned just 9% of all STEM degrees, from
          bachelor’s to doctorates, far below their 12% share of the U.S.
          population.</strong
        >
        What’s more troubling: these
        <strong>figures have barely shifted since 2010.</strong>
        <span
          ><a
            href="https://www.pewresearch.org/science/2021/04/01/stem-jobs-see-uneven-progress-in-increasing-gender-racial-and-ethnic-diversity/"
          >
            Pew Research, "STEM Jobs See Uneven Progress in Increasing Gender,
            Racial and Ethnic Diversity," April 2021</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        While Black students are especially underrepresented in math,
        engineering, and physical sciences, the gap becomes even more striking
        at the graduate level. For example, <strong
          >only 5% of research doctorates in engineering went to Black
          students in 2018, and just 2.4% of PhDs in artificial
          intelligence were awarded to Black scholars.</strong
        >
        <span
          ><a
            href="https://www.pewresearch.org/science/2021/04/01/stem-jobs-see-uneven-progress-in-increasing-gender-racial-and-ethnic-diversity/"
          >
            Pew Research, "STEM Jobs See Uneven Progress in Increasing Gender,
            Racial and Ethnic Diversity," April 2021</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        A 2021 Pew survey reveals deeper reasons: only a third of Black adults
        see STEM as welcoming or inclusive, which contributes to lower personal
        motivation and aspirational barriers. <strong
          >Many Black STEM graduates report something harder to quantify - the
          feeling of not belonging.
        </strong>
        <br />
        <ul>
          <li>
            34% say they were treated as if they couldn’t understand STEM
            subjects.
          </li>
          <li>34% say someone made them feel they didn’t belong.</li>
          <li>20% experienced racial slights or comments.</li>
        </ul>

        <span
          ><a
            href="https://www.pewresearch.org/science/2021/04/01/stem-jobs-see-uneven-progress-in-increasing-gender-racial-and-ethnic-diversity/"
          >
            Pew Research, "STEM Jobs See Uneven Progress in Increasing Gender,
            Racial and Ethnic Diversity," April 2021</a
          ></span
        >
      </ObservedArticleFadeIn>

      <ObservedArticleFadeIn>
        When asked, Black adults, especially those with higher education, point
        to
        <strong
          >a lack of mentorship and poor access to quality education as key
          barriers.
        </strong>
        About 65% of Black adults with postgraduate degrees say the absence
        of a mentor or supportive adult is a major reason why young people don’t
        go into STEM.
        <span
          ><a
            href="https://www.pewresearch.org/science/2021/04/01/stem-jobs-see-uneven-progress-in-increasing-gender-racial-and-ethnic-diversity/"
          >
            Pew Research, "STEM Jobs See Uneven Progress in Increasing Gender,
            Racial and Ethnic Diversity," April 2021</a
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
  ul {
    font-size: 18px;
    font-weight: 700;
  }
  .text p {
    color: white;
    text-align: left;
    margin: 3vh;
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
    margin-left: -12vw;
  }

  .reference {
    text-align: left;
    margin-left:1vw;
  }
  small {
    color: rgb(173, 172, 172);
  }

  h2 {
    font-family: "Raleway";
    font-weight: 500;
    font-style: normal;
    font-size: 25px;
    margin-top: 0;
    color: white;
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
