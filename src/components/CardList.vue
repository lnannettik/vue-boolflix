<template>
    <section class="section">
        <div class="col" v-for="item in list" :key="item.id">
            <Card
                :title="item.title ? item.title : item.name"
                :originalTitle="item.original_title ? item.original_title : item.original_name"
                :language="item.original_language"
                :overview="item.overview"
                :vote="item.vote_average"
                :poster="item.poster_path"
            />

        </div>
        
       
    </section>
  
</template>

<script>
import Card from "@/components/Card.vue";

export default {
    name: 'CardList',
    components: { Card },
    props: {
        list: Array,
    },

};
</script>

<style scoped lang="scss">

    .section {
        display: flex;

    }

</style>