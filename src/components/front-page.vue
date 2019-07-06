<template>
  <div class="frontPage">
    <h2>{{ pageTitle }}</h2>
    <img :src="image.link" :alt="image.altText" />
    <p v-for="text in content">
      {{ text.paragraph }}
    </p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pageTitle: "My First Vue App",
      image: {
        link:
          "https://hbr.org/resources/images/article_assets/2019/04/Apr19_16_98841838.jpg",
        altText: "Think Differently"
      },
      content: [
        {
          paragraph:
            "This story is about the friendship between a frog and a mouse and shows how your actions against others can backfire on yourself. This story will teach your child about the African saying “Don’t dig too deep a pit for your enemy, you may fall into it yourself”"
        },
        {
          paragraph:
            "Let us enjoy reading this one of African Stories of Friends Forever A mouse and a frog were friends. Every morning the frog would hop out of his pond and go to visit his friend who lived in a hole in the side of a tree. He would return home at noon.The mouse delighted in his friend’s company unaware that the friend was slowly turning into an enemy. The reason? The frog felt slighted because though he visited the mouse everyday, the mouse on his part, had never made an attempt to visit him. One day he felt he had been humiliated enough. When it was time for him to take leave of the mouse, he tied one end of a string around his own leg, tied the other end to the mouse’s tail, and hopped away, dragging the hapless mouse behind him. The frog dived deep into the pond. The mouse tried to free himself but couldn’t, and soon drowned. His bloated body floated to the top. A hawk saw the mouse floating on the pond’s surface. He swooped down, and grabbing the mouse in his talons, flew to the branch of a nearby tree. The frog, of course, was hauled out of the water too. He desperately tried to free himself, but couldn’t and the hawk soon put an end to his struggles. In Africa they have a saying: ‘Don’t dig too deep a pit for your enemy, you may fall into it yourself’. "
        }
      ]
    };
  }
};
</script>

<style>
.frontPage {
  width: 60%;
  margin: 0 auto;
}
h2 {
  font-family: "Times New Roman", Times, serif;
  font-size: 2rem;
  font-weight: bold;
  text-align: left;
}
.home {
  display: flex;
  flex-direction: column;
}
img {
  float: left;
  width: 60%;
  padding-right: 10px;
  padding-bottom: 10px;
}
h2 {
  font-size: 3rem;
  font-weight: bold;
}
p {
  text-align: justify;
  font-size: 1.2rem;
}
</style>
