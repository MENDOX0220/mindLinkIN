<template>
    <div id="teamresearch">
        <h1 id="title">팀 탐색</h1>

        <List 
        :items="data"
        :showDetail="none"
        :followText="'가입 요청'" :unfollowText="'나가기'" 
        :followEvent="none" :unfollowEvent="none" 
        />
        <div class="add" @click="none">
            <img src="../add.png" alt="">
        </div>
    </div>
</template>

<script>
import List from '../components/List'
export default {
    components:{
        List
    },
    data(){
        return{
            data: [
                {username: 1, nickname: "아이왑", specialty: "Web / 선린에서 젤 좋음", following: false},
                {username: 2, nickname: "에드캔", specialty: "찬효가 부장이니 곧 좋아질 예정", following: true},
                {username: 3, nickname: "RG", specialty: "Game", following: false},
            ],
        }
    },
    methods:{
        none(){
            alert("아직 개발 중인 기능입니다");
        },
    },
}
</script>

<style scoped>
h1{
    margin: 0;
}

#title{
    font-size: 2.5vw;

    padding-top: 2.5vw;
    padding-bottom: 2.5vw;        
}
#teamresearch{
    color: white;

    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    background-attachment: fixed;

    background-image: linear-gradient(to bottom, rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url("../mindmap.jpeg");

    text-align: center;
    font-family: 'Noto Sans KR', sans-serif;

    display: flex;
    align-items: center;
    flex-direction: column;

    width: 100vw;
    min-height: 100vh;
}

.add{
    color: white;

    background-color: black;

    box-shadow: 1px 1px 5px black;

    font-family: 'Noto Sans KR', sans-serif;

    display: flex;
    justify-content: center;
    align-items: center;

    width: 35vw;
    height: 100px;

    margin-top: 10px;
    margin-bottom: 5vw;
}
.add img{
    width: 50px;
    height: 50px;
}
</style>