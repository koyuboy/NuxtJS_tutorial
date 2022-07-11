<template>
    <section class="recipes">
        <Recipe
        v-for="recipe in recipes"
        :key="recipe.id" 
        :id="recipe.id"
        :thumbnail ="recipe.thumbnail"
        :title ="recipe.title"
        :previewText ="recipe.previewText"
         />
    </section>
</template>

<script>
import Recipe from '@/components/Recipe'

export default {
    components: {
        Recipe
    },
    asyncData(){
        return new Promise((resolve, reject)=>{
            setTimeout(()=>{
                resolve({
                    recipes: [
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
                    ]
                })
            }, 1500)
        })
    },
}
</script>


<style scoped>
.recipes{
    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;
}

</style>