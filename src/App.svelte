<script>
  import ImageCard from "./lib/ImageCard.svelte";

  let cardData = [
    {
      image:
        "https://cdn2.psychologytoday.com/assets/styles/manual_crop_16_9_1200x675/public/field_blog_entry_teaser_image/2021-07/handwriting_literacy_learning.png.jpg?itok=ByDM4Zdf",
      title: "poetry",
      description:
        "i love reading & writing poetry! in high school, i led my school's literary magazine",
    },
    {
      image:
        "https://resources.rotary5320.org/wp-content/uploads/2020/01/interact-logo.png",
      title: "volunteering",
      description: "i love to volunteer in my community, and am super involved with organizations such as Interact",
    },
    {
      image:
        "https://hips.hearstapps.com/hmg-prod/images/taylor-swift-performs-onstage-during-taylor-swift-the-news-photo-1697203216.jpg",
      title: "concerts",
      description:
        "i've seen taylor swift, conan gray, gracie abrams, maisie peters, role model, & ricky montgomery live!",
    },
  ];

  let name = "joy"; // Change this to your name
  let bio =
    "i'm a rising college freshman majoring in computer science & public affairs. i grew up in the sf bay area, but will be moving to new england for college!";
  let programs = ["web dev '21", "data science '22", "ai/ml '23", "data storytelling challenge '25"];

"scripts": {
    "dev": "vite",
    "build": "vite build",
    "deploy": "npm run build && gh-pages -d dist",
    "preview": "vite preview"
  }
</script>

<div class="container">
  <h1>a little bit about me</h1>
  <p>hey there! my name is {name} :) {bio}</p>

  <h2>my kwk journey</h2>
  <div class="programs">
    {#each programs as program}
      <div class="program">{program}</div>
    {/each}
  </div>

  <h2>hobbies & interests</h2>
  <div class="card-container">
    {#each cardData as { image, title, description }}
      <ImageCard {image} {title} {description} />
    {/each}
  </div>
</div>

<style>

  h1 {
    color: white;
    font-family: Arial, sans-serif;
  }
  .container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    text-align: left;
  }

  .card-container {
    display: flex;
    justify-content: center;
  }

  .programs {
    display: flex;
    justify-content: left;
    gap: 15px;
    flex-wrap: wrap;
  }
  .program{
    background-color: #f7bed9;
    color: white;
    padding: 10px 15px;
    border-radius: 5px;
  }
</style>
