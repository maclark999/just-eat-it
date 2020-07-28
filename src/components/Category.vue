<!-- TODO: null handling -->
<!-- TODO: add option for random all the way -->

<template>
	<div>
		<h1>Category</h1>
		<div>
			<select name="categories" id>
				<option
					v-for="category in foodCategories"
					:key="category.alias"
					:value="category.alias"
					>{{ category.title }}</option
				>
			</select>
		</div>
		<button @click="$emit('selectRestaurant')">Restaurant Please!</button>
	</div>
</template>

<script>
import tempCategoryData from "../assets/temp-data";

const yelpFoodCategories = ["restaurants", "bars"];

export default {
	name: "Category",
	data: () => ({
		tempCategoryData,
	}),
	computed: {
		// if parent category array has an object where alias is food, restaurants, bars
		// add title to array
		foodCategories: function() {
			const foodCats = tempCategoryData.reduce(
				(foodCategoryTitles, category) => {
					const categoryIsFood = category.parent_categories.some((parentCat) =>
						yelpFoodCategories.includes(parentCat.alias)
					);

					if (categoryIsFood) {
						foodCategoryTitles.push({
							title: category.title,
							alias: category.alias,
						});
					}
					return foodCategoryTitles;
				},
				[]
			);
			return foodCats;
		},
	},
};
</script>

<style></style>
