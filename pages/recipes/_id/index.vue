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
              title: "Delicious",
              previewText: "Awesomely Delicious!",
              descriptionText: "This is really a delicious meal",
              thumbnail:
                "https://static1.squarespace.com/static/5685a06669492ea07bb9b05d/t/5702d1922b8ddeaf55815b1f/1459802521539/Angel+Food-+High+Res-6766.jpg?format=1500w"
            },
            {
              id: "2",
              title: "So Good!",
              previewText: "Fantastic!",
              descriptionText: "This is really a delicious meal",
              thumbnail:
                "https://food.fnr.sndimg.com/content/dam/images/food/fullset/2018/6/0/FN_snapchat_coachella_wingman%20.jpeg.rend.hgtvcom.616.462.suffix/1523633513292.jpeg"
            }
          ].find(el => el.id === context.params.id)
        });
      }, 800);
    });
  }
};
</script>

<style scoped>
.single-recipe {
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
  flex-flow: column;
}

.recipe-image {
  max-width: 98vw;
}
</style>
