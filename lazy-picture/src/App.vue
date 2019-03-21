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
		<h2>Just img tag</h2>
		<lazy-picture :img-sources="sources[1].img" lazy />
		<lazy-picture :img-sources="sources[2].img" lazy />
  </div>
</template>

<script>
import lazyPicture from "vue-lazy-picture";

export default {
  name: "app",
  components: {
    lazyPicture
  },
  data() {
    return {
      sources: [
        {
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
				},
				{
          img: {
            src: "./images/moscow.jpg",
            placeholder: "./images/moscow-small.jpg"
					},
				},
				{
          img: {
            src: "./images/lumpur.jpg",
            placeholder: "./images/lumpur-small2.jpg"
					},
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
