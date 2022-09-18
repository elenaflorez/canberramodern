<template>
	<div class="container">
		<SiteNavigation />
		<section class="bannerContainer">
        	<img class="bannerImage" src="@/Images/BannerImage.png" alt="Banner" />
        	<div class="bannerText">
          		<h1>Canberra Modern</h1>
          		<h2>Conservation through participation </h2>
        	</div>
    	</section>
		<h2>Showcase Events</h2>
		<section class = "eventsContainer">
			<article>
				<img class="eventImage" src="@/Images/Canberra Modern Presents 1.png" alt="Banner" />
				<h2>Event 1</h2>
			</article>
			<article>
				<img class="eventImage" src="@/Images/Canberra Modern Presents 2.png" alt="Banner" />
				<h2>Event 2</h2>
			</article>
			<article>
				<img class="eventImage" src="@/Images/Canberra Modern Presents 3.png" alt="Banner" />
				<h2>Event 3</h2>
			</article>
		</section>
		<h2>Showcase Buildings</h2>
		<ShowcaseBuildings />

	</div>
</template>

<script>
export default {
	name: 'IndexPage'
}
</script>

<style>
* {
	font-family: Futura;
}

h1 {
	font-weight:950;
	font-size:5vw;
	text-align:center;
}

h2 {
	font-weight:700;
	font-style:italic;
	font-size:3vw;
}

h3 {
	font-weight:500;
	font-size:2.5vw;
}

p {
	font-size:2vw;
}

.bannerContainer {
    position: relative;
    text-align: center;
}

.bannerImage {
  width:100%
}

.eventImage {
	width:100%
}

.bannerText {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: white;
  font-size:6vw;
}

.eventsContainer {
	display: grid;
    grid-template-columns: 1fr 1fr 1fr; /*Reactive sizing for these columns */
    column-gap: 10%
}



@media only screen and (min-width: 1000px) {
    h1 {
      font-size:50px;
    }
	h2 {
		font-size:50px;
	}
  }

</style>


