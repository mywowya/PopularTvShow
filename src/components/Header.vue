<template>
    <header>
        <h1> {{ title }} </h1> <!--Title holder that changed from ./App.vue-->
    </header>
</template>

<script>
export default {
    props: ['title']
}
</script>

<style scoped>
header {
    padding: 20px 30px;
    display:flex;
    justify-content: center;
}

h1{
    font-size:32px;
    color:black;
    font-weight: 700;
    text-align: center;
    text-transform: uppercase;
}

    h1 {
        font-size: 32px;
        color: black;
        font-weight: 700;
        text-align: center;
        text-transform: uppercase;
    }
</style>