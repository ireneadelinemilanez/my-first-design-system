<!--
@component
This is your page!
-->

<script>
  // Import all the news furniture components
  import ArticleBody from '$lib/components/ArticleBody.svelte';
  import Image from '$lib/components/Image.svelte';
  import RelatedLinks from '$lib/components/RelatedLinks.svelte';
  import BigNumber from '$lib/components/BigNumber.svelte';
  import Dashboard from '$lib/components/Dashboard.svelte';

  // Article metadata
  let kicker = 'NYCity News Service';
  let headline = 'Become a Force for Good';
  let deck = "At CUNY's journalism school, change is in our DNA";
  let pubDate = 'March 9, 2026';

  // Related stories
  const relatedStories = [
    { headline: 'How America\'s top news organizations escape rigid publishing systems to design beautiful data-driven stories on deadline.', href: 'https://palewi.re/docs/coding-the-news/' },
    { headline: 'How to install, configure and use Visual Studio Code, GitHub and Copilot', href: 'https://palewi.re/docs/coding-the-news/scripts/week-1/' },
    { headline: "How to publish a website with Node.JS and GitHub Actions", href:"https://palewi.re/docs/coding-the-news/scripts/week-2/"},
  ];
</script>

<!-- This sets the page title in the browser tab -->
<svelte:head>

  <title>{headline} | NYCity News Service</title>
  <meta name="description" content="At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined." />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&display=swap" rel="stylesheet">
</svelte:head>

<!-- Your page content goes here -->
<div class="container story-theme">
  
  <div class="story-header">
    <span class="kicker">{kicker}</span>
    <h1>{headline}</h1>
    <hr class="rule" />
    <p class="deck">{deck}</p>
    <p class="byline">{pubDate}</p>
  </div>

  <!-- Lead Image: Animated gif of students at the journalism school -->
  <Image
    src="/example-photo.gif"
    alt="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    caption="The Craig Newmark Graduate School of Journalism is at 219 West 40th Street in Midtown Manhattan."
    credit="Craig Newmark Graduate School of Journalism"
  />

    <Dashboard>
    <BigNumber
      number="2006"
      label="Year Founded"
    />
    <BigNumber
      number="1,300"
      label="Alumni"
    />
    <BigNumber
      number="50%"
      label="Attend tuition free"
      footnote="As of Aug. 2025"
    />
    </Dashboard>

  <!-- Article Body: The main story text with proper typography -->
  <ArticleBody>
    <p>
      At the Craig Newmark Graduate School of Journalism at the City University of New York, change is in our DNA. That comes of being born in 2006, as the digital revolution was transforming our profession in ways none of us could have imagined.
    </p>

    <p>
      We fashioned a school to teach the latest storytelling, entrepreneurial, and technological skills alongside reporting, writing, and ethics. Beyond that, we’ve crafted a culture that spurns complacency, that isn’t afraid to pivot before the ground under us shifts.
    </p>

    <p>
      Our mission is to serve the public interest – by training new journalists from varied economic, racial, and cultural backgrounds who will bring much-needed diversity to newsrooms, by helping mid-career journalists retool their skills, and by partnering with other media organizations to find new paths to excellence.
    </p>

    <p>
      Our low tuition rates, along with the added backing of private donors, allow candidates for our master’s degrees in journalism and engagement journalism to receive a world-class education at an affordable price. We also offer a unique bilingual master’s in journalism for students fluent in English and Spanish.
    </p>

    <p>
      Our three media centers provide research, training, thought leadership, industry meet-ups, and financial support for quality journalistic work.
    </p>

    <p>
      We also offer a robust professional education program through regular evening and weekend workshops. And we support in-depth reporting projects of professional journalists through fellowship grants.
    </p>

    <p>
      Classes are led by accomplished full-time faculty and adjuncts, who tap their networks to help students and graduates find internships, freelance opportunities and — the ultimate prize — jobs.
    </p>

    <p>
      At a time when our profession is reeling from financial pressures and lack of trust, the Newmark Graduate School of Journalism is committed to producing the next generation of skilled, ethically minded, and diverse journalists.
    </p>

    <p>
      We invite you to be part of our world.
    </p>
  </ArticleBody>

  <!-- Related Stories: Links to other articles -->
  <RelatedLinks
    title="Related Stories"
    links={relatedStories}
  />

</div>

// Style overrides global color theme

<style lang="scss">
  @use '$lib/styles' as *;

  :global(.story-theme) {
    --color-accent: #fe8807;
    --color-border: #fe8807;

    .story-header {
      text-align: center;
      padding: var(--spacing-xxl) var(--spacing-md);
    }

    .kicker {
      display: block;
      font-family: var(--font-sans);
      font-size: var(--font-size-xs);
      text-transform: uppercase;
      letter-spacing: 0.15em;
      color: var(--color-accent);
      margin-bottom: var(--spacing-sm);
    }

    .story-header h1 {
      font-family: 'Playfair Display', Georgia, serif;
      font-size: var(--font-size-4xl);
      font-weight: 900;
      line-height: var(--leading-tight);
      color: var(--color-dark);
      margin-bottom: var(--spacing-sm);
    }

    .rule {
      border: none;
      border-top: var(--border-width-accent) solid var(--color-accent);
      width: 60px;
      margin: 0 auto var(--spacing-sm);
    }

    .deck {
      font-family: var(--font-serif);
      font-size: var(--font-size-lg);
      line-height: var(--leading-normal);
      color: var(--color-text);
      max-width: 480px;
      margin: 0 auto var(--spacing-sm);
    }

    .pubdate {
      font-family: var(--font-sans);
      font-size: var(--font-size-sm);
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: var(--color-medium-gray);
    }

    @include mobile {
      .story-header h1 {
        font-size: var(--font-size-3xl);
      }

      .deck {
        font-size: var(--font-size-lg);
      }
    }
}
</style>
