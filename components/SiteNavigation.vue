<!-- this component can hold site navigation -->
<!-- if we put it here we can avoid having to repeat the code -->
<template>
	<nav>
  <NuxtLink to="/">
      Home
    </NuxtLink>
    <NuxtLink to="/about">
      About
    </NuxtLink>
		<NuxtLink to="/buildings">
      Buildings
    </NuxtLink>
    <NuxtLink to="/events">
      Events
    </NuxtLink>
	</nav>
</template>
<script>

</script>

<!--You can put whatever you want down here to affect the styling of the nav-->
<style>
  
</style>