<template>
    <div>
        <div class="home">Home</div>
        <router-link to="/List" class="home">列表页</router-link>
    </div>
</template>

<script>
export default {
    name:"Home"
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
}

.home{
    font-size: 50px;
}
</style>


