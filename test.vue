<template>
    <div class="test">
        <div class="box">
            <div class="left">
                <div>
                    <div ref="d1" class="d1" :class="{active:isActive}" @click="scale">1</div>
                </div>
                <div>2</div>
            </div>
            <div class="right">3</div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            isActive:false
        }
    },
    methods:{
        scale(){
            this.isActive=!this.isActive
        }
    }
}
</script>
<style>
.test{
    width:100%;
    height:100%;
}
.box{
    width:100%;
    height:auto;
    display:flex;
}
.box .left{
    width:30%;
    display: flex;
    flex-direction: column;
}
.box .right{
    width:70%;
    background:red;
    padding-top:70%;
}
.box .left>div:first-child{
    background:green;
    height:50%;
    margin-right: 5px;
    margin-bottom: 5px;
    position: relative;
}
.box .left>div:first-child .d1{
    background:gray;
    width:100%;
    height:100%;
    position: absolute;
    transition: all 0.3s linear;
}
.box .left>div:first-child .active:hover{
    transform:scale(2,2);
    z-index: 999;
    -webkit-transform: scale(2,2);
}
.box .left>div:last-child{
    background:orange;
    height:50%;
    margin-right: 5px;
}

</style>
