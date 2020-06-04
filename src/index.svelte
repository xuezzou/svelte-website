<script>
  // for svg and page animation effect
  import { draw, fade, fly } from "svelte/transition";
  import { expand } from "./custom-transitions.js";
  import FAQ from "./faq.svelte";
  import Schedule from './schedule.svelte';
  import Countdown from './countdown.svelte';
  import Links from './links.svelte';
  import Cards from './cards.svelte';

  // type writer effect
  function typewriter(node, { delay = 0, speed = 70 }) {
    const valid =
      node.childNodes.length === 1 &&
      node.childNodes[0].nodeType === Node.TEXT_NODE;

    if (!valid) {
      throw new Error(
        `This transition only works on elements with a single text node child`
      );
    }

    const text = node.textContent;
    const duration = text.length * speed;

    return {
      delay,
      duration,
      tick: t => {
        const i = ~~(text.length * t);
        node.textContent = text.slice(0, i);
      }
    };
  }

  // placeholder url for all links in the page
  const vhPlaceholderURL = "https://vandyhacks.org/";

  const introText = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."

  // TODO 
  // define faq items
  const questionSetLeft = [
    {
      question: "Who can apply?",
      answer:
        "Anyone who is 18 years or older (we will be checking ID) and is currently enrolled in college or university with a valid student ID. International students are invited to apply and attend, but we cannot guarantee full travel reimbursement."
    },
    {
      question: "How does registration work?",
      answer:
        "Applications are now open! Acceptance is determined by a variety of factors, and applications will be reviewed by our board on a rolling basis. Once you’re accepted, you’ll receive an email from the VandyHacks team. If you're curious, email us for more info at"
    },
    {
      question: "What if I'm a Vanderbilt student?",
      answer:
        "All Vanderbilt students are encouraged to attend, regardless of major or background."
    },
    {
      question: "Are walk-ins allowed?",
      answer:
        "We ask that everyone complete an application, but walk-ins will be accepted if space allows. We cannot guarantee swag for walk-ins."
    },
    {
      question: "How do I get there?",
      answer:
        "Cars, buses, or flights, depending on location! We'll be sending buses to specific schools with large numbers of applicants."
    },

    {
      question: "I have more questions!",
      answer:
        "Send us an email at info@vandyhacks.org! We'll be happy to answer!"
    }
  ];
  const questionSetRight = [
    {
      question: "What is a hackathon?",
      answer:
        "Hackathons are events where students from across the country come together for a weekend of innovation and creativity. Participants have 36 hours to create anything that shows off their creativity and passion for development. You may choose any platform, programming language, or format to show your stuff. You can even present a storyboard or idea; there’s no end to the possibilities!"
    },
    {
      question: "I have no idea how to code. Can I still attend?",
      answer:
        "Even more reason for you to come! We will be hosting beginners' workshops for you to get started, and our mentors can help you out along the way. We greatly encourage new hackers to attend, and no prior experience is necessary!"
    },
    {
      question: "What if I've never been to a hackathon?",
      answer:
        "Not to worry! A few weeks before the event, you’ll receive an email with a link to our hacker guide, which will contain all the information you need to make the most out of your weekend. During the event, the VandyHacks Team will be around to help answer any questions. As always, feel free to email us at"
    },
    {
      question: "How are teams formed? Do I need a team?",
      answer:
        "Teams are limited to four people. If you're applying with a team, we will review all of your team members' applications to determine admission. We will also have a pitch session where attendees can share their ideas and find potential teammates. However, teams are not required, so feel free to work individually."
    },
    {
      question: "Will there be other activities besides hacking?",
      answer:
        "Of course! This year, we've planned a bunch of fun events for attendees to relax. Stay tuned for more info!"
    },
    {
      question: "What if I’m interested in being a mentor?",
      answer: "Send us an email at: "
    }
  ];
</script>

<style>

  a {
    color: #bbbbc4;
    text-decoration: none;
    -o-transition: 0.5s;
    -ms-transition: 0.5s;
    -moz-transition: 0.5s;
    -webkit-transition: 0.5s;
    transition: 0.5s;
  }

  a:hover {
    color: #ffdb73;
  }

  h1 {
    color: #ffdb73;
    padding-bottom: 0px;
    margin-bottom: 1%;
    font-family: "Varela Round", sans-serif;
  }

  h2 {
    color: #555560;
    font-size: 3rem;
    font-weight: bold;
    margin: 0px;
    padding: 0px;
  }

  .logo {
    color: white;
    padding: 5rem 0 2rem 0;
    min-width: 800;
  }

  .top {
    padding-bottom: 5rem;
  }

  .intro {
    color: #bbbbc4;
    font-size: 1.8rem;
    line-height: 180%;
  }

  .pulled {
    margin-bottom: 9rem;
  }

  .pulled h1 {
    color: white;
    font-size: 3rem;
  }

  .footer {
    padding-top: 5rem;
  }

  .footer p {
    color: white;
    font-size: 1.2rem;
  }

  .visit {
    color: white;
    font-size: 1.5rem;
    background: #32333a;
    width: 12rem;
    padding: 6px;
    border-radius: 10px;
    position: fixed;
    right: 20px;
    text-align: center;
    z-index: 2;
  }

  .header-space {
    height: 4rem;
  }

  /* Mobile first queries */

  /* Larger than mobile */
  @media (min-width: 400px) {
  }

  /* Larger than phablet */
  @media (min-width: 550px) {
  }

  /* Larger than tablet */
  @media (min-width: 750px) {
  }

  /* Larger than desktop */
  @media (min-width: 1000px) {
  }

  /* Larger than Desktop HD */
  @media (min-width: 1200px) {
    h1 {
      font-size: 4rem;
    }
  }
</style>

<div class="visit" transition:fade={{ duration: 2000 }}>
  <a href="https://apply.vandyhacks.org/" target="_blank">Register here!</a>
</div>
<div id="particles-js">
  <div class="container">
    <div class="row top">
      <div class="twelve column">
        <div class="logo">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            id="Layer_1"
            data-name="Layer 1"
            viewBox="0 0 430 430" width="9rem" height="9rem">
            <g>
              <path
                style="stroke:#fff; fill:#282931; stroke-width:0.1rem;"
                in:draw={{ duration: 3000 }}
                d="M1259.83 782.15h-18.44a7.3 7.3 0 00-6.38 4.44l-77.7
                209.65-78-209.64a7.32 7.32 0 00-6.39-4.44h-18.44a3.07 3.07 0
                00-3.09 4.44l91.19 245.18a6 6 0 00.93 1.6l-9.83
                26.53-101.27-273.3a7.3 7.3 0 00-6.38-4.44h-18.44a3.08 3.08 0
                00-3.09 4.44l114.16 308a6.59 6.59 0 001.92 2.63 3.1 3.1 0 003.24
                2.13h18.44a6.13 6.13 0 002.11-.41 3.18 3.18 0 001.64-.85 6.91
                6.91 0 002.63-3.19l114.28-308.32a3.08 3.08 0
                00-3.09-4.45zM1354.93 782.15h-18.44a7.3 7.3 0 00-6.38
                4.44L1215.83 1095a3.08 3.08 0 003.09 4.44h18.44a7.31 7.31 0
                006.38-4.44L1358 786.6a3.08 3.08 0 00-3.07-4.45zM1240.89
                960.6h-18.44a7.3 7.3 0 00-6.38 4.44L1167.92 1095a3.07 3.07 0
                003.06 4.44h18.51a7.31 7.31 0 006.3-4.33L1244 965a3.07 3.07 0
                00-3.11-4.4zM1229.63 940.83h18.44a7.3 7.3 0 006.38-4.44L1310
                786.48c.77-2.07-.11-3.8-2-4.29a3.89 3.89 0 00-.42 0H1288a5.22
                5.22 0 00-1.5.25 7.78 7.78 0 00-3.3 2.28 5.24 5.24 0 00-.78
                1.37l-56.1 151.37c-.25 1.91 1.07 3.37 3.31 3.37z"
                class="cls-1"
                transform="translate(-1004.22 -782.15)" />
            </g>
            <g>
              <path
                style="fill:#fff"
                in:expand={{ duration: 4000, delay: 1000 }}
                d="M1259.83 782.15h-18.44a7.3 7.3 0 00-6.38 4.44l-77.7
                209.65-78-209.64a7.32 7.32 0 00-6.39-4.44h-18.44a3.07 3.07 0
                00-3.09 4.44l91.19 245.18a6 6 0 00.93 1.6l-9.83
                26.53-101.27-273.3a7.3 7.3 0 00-6.38-4.44h-18.44a3.08 3.08 0
                00-3.09 4.44l114.16 308a6.59 6.59 0 001.92 2.63 3.1 3.1 0 003.24
                2.13h18.44a6.13 6.13 0 002.11-.41 3.18 3.18 0 001.64-.85 6.91
                6.91 0 002.63-3.19l114.28-308.32a3.08 3.08 0
                00-3.09-4.45zM1354.93 782.15h-18.44a7.3 7.3 0 00-6.38
                4.44L1215.83 1095a3.08 3.08 0 003.09 4.44h18.44a7.31 7.31 0
                006.38-4.44L1358 786.6a3.08 3.08 0 00-3.07-4.45zM1240.89
                960.6h-18.44a7.3 7.3 0 00-6.38 4.44L1167.92 1095a3.07 3.07 0
                003.06 4.44h18.51a7.31 7.31 0 006.3-4.33L1244 965a3.07 3.07 0
                00-3.11-4.4zM1229.63 940.83h18.44a7.3 7.3 0 006.38-4.44L1310
                786.48c.77-2.07-.11-3.8-2-4.29a3.89 3.89 0 00-.42 0H1288a5.22
                5.22 0 00-1.5.25 7.78 7.78 0 00-3.3 2.28 5.24 5.24 0 00-.78
                1.37l-56.1 151.37c-.25 1.91 1.07 3.37 3.31 3.37z"
                class="cls-1"
                transform="translate(-1004.22 -782.15)" />
            </g>
          </svg>
        </div>
        <h1 transition:typewriter={{ delay: 1000 }}>June Mini-Hackathon</h1>
        <h2 transition:typewriter={{ delay: 2600 }}>Coming June 27, 2020</h2>
      </div>
    </div>

    <div class="row">
      <div class="two-thirds column">
        <div class="pulled intro">
          <h1>Welcome!</h1>
          <p>{introText}</p>
        </div>
       </div>

       <!-- countdown -->
       <div class="one-third column">
       <h1>countdown!!!!!</h1>
       </div>
    </div>

    <div class="row">
      <div
        class="one-half column"
        transition:fly={{ x: -200, duration: 2000, delay: 4000 }}>
        <div class="pulled">
          <h1>FAQ</h1>
          <FAQ questionSet={questionSetLeft} identifier="left" />
        </div>
      </div>

      <div
        class="one-half column"
        transition:fly={{ x: 200, duration: 2000, delay: 4500 }}>
        <div class="pulled">
          <div class="header-space" />
          <FAQ questionSet={questionSetRight} identifier="right" />
        </div>
      </div>
    </div>

    <div class="row">
      <div class="one-third column pulled">
        <h1>Links</h1>
        <Links />
      </div>

      <div class="two-thirds column pulled">
        <h1>Schedule</h1>
        <Schedule />
      </div>
    </div>

    <div class="row">
      <div class="pulled">
        <h1>Non-profic projects</h1>
        <Cards  />
      </div>
    </div>
  </div>
ß
  

  <!-- count down and resource link goes here -->

  <div class="container">
    <div
      class="footer"
      transition:fly={{ y: 200, duration: 2000, delay: 5000 }}>
      <p>
        Made with ♡ using the awesome
        <a
          target="_blank"
          href="https://github.com/VincentGarreau/particles.js/"
          rel="noreferrer">
          Particles.js
        </a>
        &
        <a target="_blank" href="https://getskeleton.com/" rel="noreferrer">
          Skeleton.css
        </a>
        by
        <a target="_blank" href="https://vandyhacks.org/" rel="noreferrer">
          VandyHacks
        </a>
        (๑¯◡¯๑)
      </p>
    </div>
  </div>

</div>
