<template>
  <div id="app">
    <h1>Lazy loading demo</h1>
    <p><em>Resize window to see how it works!</em></p>
    <h2>Pic 1: without fallback</h2>
    <p>Data used:</p>
    <pre>
    &lt;lazy-picture :picture-sources="sources[0].picture" lazy&gt;
        
    {
        picture: [
          {
            media: "(max-width: 480px)",
            srcset: "./images/New_york_times_square-terabass_480@1x.jpg, ./images/New_york_times_square-terabass_480@2x.jpg 2x",
            placeholder:
              "./images/New_york_times_square-terabass_480@0x.jpg"
          },
          {
            media: "(min-width: 481px)",
            srcset: "./images/New_york_times_square-terabass.jpg",
            placeholder:
              "./images/rsz_new_york_times_square-terabass-small.jpg"
          }
        ]
      }
    </pre>
    <lazy-picture :picture-sources="sources[0].picture" lazy />
  </div>
</template>

<script>
import lazyPicture from "./components/LazyPicture.vue";

export default {
  name: "app",
  components: {
    lazyPicture
  },
  data() {
    return {
      sources: [
        {
          // img: {
          //   src: "./images/New_york_times_square-terabass.jpg",
          //   placeholder: "./images/rsz_new_york_times_square-terabass-small.jpg"
          // },
          picture: [
            {
              media: "(max-width: 480px)",
              srcset:
                "./images/New_york_times_square-terabass_480@1x.jpg, ./images/New_york_times_square-terabass_480@2x.jpg 2x",
              placeholder: "./images/New_york_times_square-terabass_480@0x.jpg"
            },
            { 
              media: "(min-width: 481px)",
              srcset: "./images/New_york_times_square-terabass.jpg",
              placeholder:
                "./images/rsz_new_york_times_square-terabass-small.jpg"
            }
          ]
        }
      ]
    };
  }
};
</script>
<style>
pre {
  overflow: auto;
}
</style>
