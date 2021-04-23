<template>
  <section class="single-recipe">
    <h1>{{ recipe.title }}</h1>
    <div>
      <img class="recipe-image" :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          recipe: [
            {
              id: "1",
              title: "Delicious Pancakes",
              previewText: "Awesome Pancakes!",
              descriptionText: "This is very delicious!",
              thumbnail: "https://www.ndtv.com/cooks/images/pancakes.jpg"
            },
            {
              id: "2",
              title: "Chocolate Donuts",
              previewText: "Awesome Donuts!",
              descriptionText: "This is very delicious!",
              thumbnail: "https://dashofsanity.com/wp-content/uploads/2017/05/TRIPLE-CHOCLATE-BAKED-DONUTS-FEATURED-1.jpg"
            }
          ].find(el => el.id === context.params.id)
        })
      }, 1500)
    })
  }
}
</script>


<style scoped>
.single-recipe {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}

.recipe-image {
  width: 100%;
}
</style>
