<template>
    <div id="list">
        <div class="list-item" v-for="(item, idx) in items" :key="item.username">
            <img class="image" src="../test_pi.jpg" alt="" @click="showDetail(item, idx)">
            <span class="name" @click="showDetail(item, idx)">{{item.nickname}}</span>
            <span class="specialty">{{item.specialty}}</span>
            <span class="follow" style="color: red" v-if="item.following" @click="unfollowEvent(item, idx)">{{unfollowText}}</span>
            <span class="follow" style="color: green" v-else @click="followEvent(item, idx)">{{followText}}</span>
        </div>
    </div>
</template>

<script>
export default {
    props:{
        items: Array,

        showDetail: Function,

        followText: String,
        unfollowText: String,

        followEvent: Function,
        unfollowEvent: Function,
    },
}
</script>

<style scoped>
#list{
    display: flex;
    align-items: center;
    flex-direction: column;
}

.list-item{
    color: white;

    background-color: black;

    box-shadow: 1px 1px 5px black;

    font-family: 'Noto Sans KR', sans-serif;

    display: flex;
    align-items: center;

    width: 35vw;
    height: 100px;

    margin: 10px auto;
}

.list-item .image{
    width: 70px; 
    height: 70px;
    object-fit: cover;
    border-radius: 50%;

    margin-left: 1vw;
    margin-right: 1vw;

    cursor: pointer;
}
.list-item .name{
    font-size: 1.5vw;

    margin-right: 0.5vw;

    cursor: pointer;
}
.list-item .specialty{
    color: gray;

    font-size: 1vw;
}
.list-item .follow{
    font-size: 1vw;

    margin-left: auto;
    margin-right: 1vw;

    cursor: pointer;
}
</style>