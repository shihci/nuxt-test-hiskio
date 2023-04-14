<script>
export default{
    head(){
        return{
            title: this.name,
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: '這是關於我們的頁面'
                }
            ],
        }
    },data(){
        return{
            name:"jacky"
        }
    }
}
</script>
<template>
    <div>
        <nuxt-link to="/">Home</nuxt-link>
        <nuxt-link to="/about">About</nuxt-link>
        <h1>About</h1>
    </div>
    
</template>