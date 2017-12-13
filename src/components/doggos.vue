<template>
<div>
<img :src="doggo" />
<p>a good pupper</p>
</div>
</template>

<script>
export default {
    data () {
        return {
            doggo: '',
            thing: 'asdfasd'
        }
    },
    mounted() {
        this.getDoggo();
    },
    methods: {
        getDoggo: function(){
            let app = this;
            fetch('https://dog.ceo/api/breed/pug/images/random', { method: 'GET'}).then((res) => res.json()).then(function(json){ app.doggo = json.message; })
        }
    }
}
</script>

<style lang="scss" scoped>
div { text-align: center; font-family: sans-serif; }
img { max-width: 300px; }
</style>