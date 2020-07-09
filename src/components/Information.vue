<template>
    <div class="section">
        <p class="heading">{{ data.selectedTab }}</p><br>
        <div>
            <p class="txt-info">{{ data.info }}</p><hr><br>
            <div v-for="(paper, index) of data.list" :key="index">
                <li v-if="paper.link" class="list-papers"> {{paper.text}} <a :href="paper.link"> (...Read paper)</a> </li>
                <li v-if="paper.venue" class="list-papers">{{paper.text}} : <label class="venue">{{paper.venue}}</label></li>
                <p style="margin-top:20px;" class="txt-info" v-if="!paper.link && !paper.venue">{{paper.text}}</p>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'information',
    props:{
        data: {
            type: Object,
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
    padding: 0;
}
.list-papers{
    font-size: 16px;
   list-style-type: disc;
   line-height: 2em;
}
.list-papers:hover{
    background-color: yellow;
    cursor: pointer;
}
.list-papers a{
    text-decoration: none;
}
.venue{
    color: #F44336;
}
</style>