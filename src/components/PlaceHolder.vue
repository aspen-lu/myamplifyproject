<template>
    <div class="place-holder">
        <div class="input-div" v-for="(placeholder, index) in placeholders" :key="index">
            <input class="input" :placeholder="placeholder.title" v-model="placeholder.content">
            <!-- <input v-if="placeholder.title !== `Select Security Question`"  class="input" :placeholder="placeholder.title" v-model="placeholder.content"> -->
            <!-- <input v-else class="input input-question" :placeholder="selectedQue" :click="toggleDropdown"> -->
            <!-- <img id="arrow-down" v-if= "placeholder === 'Select Security Question'" src="../assets/dropdown.png" alt="">
            <div id="dropdown-div" v-show="isShow && placeholder.title === 'Select Security Question'" >
                <div v-for="(que, index) in securityQ" :key="index" :click="selectQ(que)">{{que}}</div>
            </div> -->
        </div>
    </div>
</template>

<script>
export default {
    props:{
        placeholders:Array
    },
    data() {
        return {
            isShow:true,
            selectedQ:"Select Security Question",
            securityQ:["Select Security Question","What was the name of your pet?", "What year did you graduate from high school?",
                       "In what city were you born?", "What street did you live on in third grade?", "What was the last name of your third grade teacher?",
                       "Who is your favorite sports team?"]
        }
    },
    computed:{
        selectedQue () {
            return this.selectedQ
        }
    },
    // methods: {
    //     toggleDropdown() {
    //         this.isShow = !this.isShow
    //     },
    //     selectQ (que) {
    //         this. selectedQ = que
    //         this.isShow = false
    //     }
    // }

}
</script>

<style scoped>
    .place-holder{
        margin: auto;
    }
    .input-div{
        padding: 15px 0;
        position: relative;
    }
    .input{
        width: 86%;
        padding: 8px 8px;
        border-radius: 4px;
        border: 1px solid rgba(0,0,0,0.125);
    }

    #arrow-down{
        position: absolute;
        width: 15px;
        right: 6%;
        top: 37%;
    }

    #dropdown-div{
        position: absolute;
        background: white;
        border: 1px solid rgba(0,0,0,0.125);
        top: 75%;
        left: 5%;
        z-index: 1;
        font-weight: 400;
    }
    #dropdown-div div{
        padding: 8px 8px;
        text-align: left;
    }
    #dropdown-div div:hover{
      background: #ababfb;
      color: white;
      cursor: pointer;
    }

</style>
