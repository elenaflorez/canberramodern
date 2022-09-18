<template>
	<div class="container">

		<SiteNavigation />
		<header>
			<h1>{{  building[0].title.rendered  }}</h1>
			<h2>{{ building[0].acf.year }}</h2>
		</header>
		<section class="buildingInfoContainer">
			<article class="buildingInfo address">
				<h3>
					Address:
				</h3>
				<p>
					{{  building[0].acf.location  }}
				</p>
			</article>
			<article class="buildingInfo suburb">
				<h3> 
					Suburb:
				</h3>
				<p>
					{{  building[0].acf.suburb  }}
				</p>
			</article>
			<article class="buildingInfo architect">
				<h3> 
					Architect:
				</h3>
				<p>
					{{  building[0].acf.architect[0].name  }}
				</p>
			</article>
		</section>

		<section>
			<h2>Related Events</h2>
			<RelatedEvents />
		</section>

		<section>
			<h2>Related Buildings</h2>
			<RelatedBuildings />
		</section>

		<section class="diveIn">
			<aside>
				<img class="" src="@/Images/CM Diving Board.png" alt="Banner" />
			</aside>
			<section>
				<h3>Want to Dive In and get involved with this landmark and others like it?</h3>
			</section>
		</section>

		<div class="building">
			<!-- the buiding returns an array with one item in it, so need to reference it below -->
			<h2>{{  building[0].title.rendered  }}</h2>

			<ul>
				<li>Address: {{  building[0].acf.location  }}</li>
				<li>Suburb: {{  building[0].acf.suburb  }}</li>
				<li>Architect: {{  building[0].acf.architect[0].name  }}</li>
			</ul>
			<!-- <pre>{{ $data }}</pre> -->
			{{building[0]}}
		</div>
	</div>
</template>

<script>
// in this API call, we go get a specifci building, filtered by the ID in the URL
// we access what is in the URL by using the params object
export default {
	async asyncData({ params }) {
		const building = await fetch(
			// `http://cm.beneb.com/wp-json/wp/v2/buildings/142`
			//`https://cm.beneb.com/wp-json/wp/v2/buildings/?slug=high-court-of-australia`
			`http://cm.beneb.com/wp-json/wp/v2/buildings/?slug=${params.slug}`
		).then((res) => {
			if (res.ok) {
				return res.json()
			}
			throw new Error(res.status)
		})
		return { building }
	},
}
</script>

<style>
	.buildingInfoContainer {
		display: flex;
		align-items: center;
		flex-direction: row;
		text-align:center;
		align-items: center;
		/* flex-grow:1;
		width:100%; */
		/* justify-content: space-between; */
	}
	.address {
		background-color: #eda384;
		color:white;
		text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
		flex-grow:1;
	}
	.suburb {
		background-color: #7087c2;
		color:white;
		text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
		flex-grow:1;
	}
	.architect {
		background-color: #f27075;
		color:white;
		text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
		flex-grow:1;
	}
	.diveIn {
		display:grid;
		grid-template-columns: 1fr 2fr;
	}

</style>
