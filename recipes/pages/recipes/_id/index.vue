<template>
    <section class="single-recipe">
        <h1>{{recipe.title}}</h1>
        <div>
            <img class="recipe-img" :src="recipe.thumbnail" :alt="recipe.title">
        </div>
        <p>{{recipe.previewText}}</p>
    </section>
</template>

<script>
export default {
    asyncData(context){
        return new Promise((resolve, reject)=>{
            setTimeout(()=>{
                resolve({
                    recipe: [
                        {
                            thumbnail: "https://imgrosetta.mynet.com.tr/file/11920486/11920486-728xauto.jpg",
                            title: "Pizza",
                            id: "1",
                            previewText: "Pizza is super."
                        },
                        {
                            thumbnail: "https://cdn.yemek.com/mnresize/940/940/uploads/2017/08/tikka-masala-tavuk-tarifi.jpg",
                            title: "Tikka Masala",
                            id: "2",
                            previewText: "Indian chicken food."
                        }
                    ].find(x => x.id === context.params.id)
                })
            }, 1500)
        })
    },
}
</script>

<style scoped>
.recipe-img{
    width: 100%;
}

.single-recipe{
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 30px;
}
</style>