<template>
    <div>
        <h1>Search Result for {{ $route.params.id }}</h1>
            <div v-if="albumExists">
                <div v-for="(album, index ) in $store.state.albums" :key="album" :key2="index">
                    <Card
                        :title="album.collectionCensoredName"
                        :image="album.artworkUrl100"
                        :artistName="album.artistName"
                        :url="album.collectionViewUrl"
                        :color="picker(index)"
                    />
                </div>
                {{$store.state.albums}}
            </div>
            <div v-else>
                <h1>No Album Found.</h1>
            </div>
    </div>
</template>
<script>
import Card from '~/components/Card.vue';
export default {
    components:{
        Card
    },
    middleware: 'search',
    computed: {
        albumExists(){
        return this.$store.state.albums.length  > 0;
    }
    },
    methods:{
        picker(index){
            return index % 2 == 0 ? '#8A8BD4' : '#9D649B';
        }
    },
}
</script>