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

	</div>
</template>

<script>
export default {
	name: 'IndexPage'
}
</script>

<style>
	.bannerContainer {
    position: relative;
    text-align: center;
}

.bannerImage {
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
</style>
