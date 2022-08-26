<template>
    <div class="about">
        <div v-if="book"
            className="w-3/12 p-3 m-auto bg-slate-50 mt-4 shadow-2xl flex justify-center flex-col items-center">
            <h3 className="text-2xl text-gray-900 uppercase">{{ book.title }}</h3>
            <h3 className="text-gray-800">By {{ book.author }}</h3>
            Book {{ book.series.sequence }} of {{ book.series.title }}
            <!-- <div class="flex justify-center">
                <img className="w-48" :src="pokemon.sprites.front_shiny" alt="" />
                <img className="w-48" :src="pokemon.sprites.back_shiny" alt="" />
            </div>
            <h3 class="text-yellow-400">Types</h3>
            <div v-for="(type, idx) in pokemon.types" :key="idx">
                <h5 class="text-blue-900">{{ type.type.name }}</h5>
            </div> -->
        </div>
    </div>
</template>

<script>
import { reactive, toRefs } from "vue";
import { useRoute } from "vue-router";
export default {
    setup() {
        const route = useRoute();
        const book = reactive({
            book: null
        });
        fetch(`/api/v1/book/${route.params.slug}`)
            .then((res) => res.json())
            .then((data) => {
                book.book = data;
                console.log(data);
            });
        return { ...toRefs(book) };
    }
};
</script>