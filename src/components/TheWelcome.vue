<script setup></script>

<template>
    <h3>#Project List</h3>
    <div class="tab">
        <button>All</button>
        <button>frontEnd</button>
        <button>UI/UX</button>
        <button>BackEnd</button>
    </div>
    <div class="list">
        <div class="box">
        </div>
        <div class="box">
            <div class="mask"></div>
            <div class="dot"></div>
        </div>
        <div class="box"></div>
    </div>
</template>

<style lang="scss">

h3{
    font-size: 25px;
    font-weight: bold;
    text-transform:uppercase;
    padding-bottom: 10px;
    border-bottom: 1px solid red;
}

.tab {
    margin-top: 20px;
    text-align: center;

    button {
        border: none;
        background-color: transparent;
        cursor: pointer;
        font-size: 16px;
        margin: 0 15px;

        &.active {
            text-decoration: underline;
        }
    }
}

.list {
    margin-top: 20px;
    display: flex;
    flex-wrap: wrap;
    gap: 1em;

    .box {
        width: 250px;
        height: 250px;
        flex: 1 1 auto;
        overflow: hidden;
        border: 1px solid #1b1b1b;
        position: relative;
        cursor: pointer;

        // .mask{
        //     position: absolute;
        //     top: 0px;
        //     left: 0px;
        //     width: 100%;
        //     height: 100%;
        //     z-index: 2;
        //     background-color: rgba(0,0,0,.5);
        //     transition: all ease-in-out .5s;
        //     &:hover{

        //         display: none;
        //     }
        
           
        // }

        img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            filter: grayscale(100%) brightness(50%);
            transition: all ease-in-out .5s;
            &:hover{
                filter: grayscale(0%) brightness(1) ;
            }
        }

    }
}
</style>
