<template>
	<div>
		<h1>Location</h1>
		<div class="range-slider">
			<input
				class="range-slider__range"
				type="range"
				value="100"
				min="800"
				max="40000"
				step="50"
				@change="updateValue($event)"
				@input="updateValue($event)"
			/>
		</div>
		<div class="range-slider__value">{{ sliderValue }}</div>
		<button @click="$emit('updateStep')">Next</button>
	</div>
</template>

<script>
export default {
	name: "Location",
	data: () => ({
		sliderValue: 0,
	}),
	methods: {
		updateValue: function(event) {
			// yelp API requires location radius value in meters
			const valueInMiles = event.target.value * 0.000621;
			this.sliderValue = (Math.round(valueInMiles * 4) / 4).toFixed(2);
		},
	},
};
</script>

<style></style>
