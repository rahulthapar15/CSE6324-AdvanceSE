<template>
    <div class="section">
        <p class="heading">{{ data }}</p>
    </div>
</template>
<script>
export default {
    name: 'information',
    props:{
        data: {
            type: String,
            required: false
        }
    },
}
</script>
<style scoped>
.heading{
    font-size: 26px;
    font-weight: 900;

}
.section{
    margin-top: 30px;
}
</style>