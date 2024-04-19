
<template>
    <h3>#Project List</h3>
    <div class="tab">
        <button>All</button>
        <button>FrontEnd</button>
        <button>UI/UX</button>
        <button>BackEnd</button>
    </div>
    <div class="list">
        <div class="box" v-for="(item, idx) in list" :key="idx" @click="openItem(idx)">
            <img :src="item.thumbnail" :alt="item.name">
        </div>
    </div>

    <div class="itemWrap" v-if="this.open == true">
        <button class="close">
            <div class="c1"></div>
            <div class="c2"></div>
        </button>
        <div class="itemBg">
            <div v-if="currentIndex !== null">
            <h1>{{ list[currentIndex].name }}</h1>
            <p>日期: {{ list[currentIndex].date }}</p>
            <p>使用技能: {{ list[currentIndex].skill }}</p>
            <p>負責: {{ list[currentIndex].respon }}</p>
            <a :href="list[currentIndex].link" target="_blank">更多資訊</a>
        </div>
        </div>
    </div>
</template>

<style lang="scss">
h3 {
    font-size: 25px;
    font-weight: bold;
    text-transform: uppercase;
    padding-bottom: 10px;
    border-bottom: 1px solid #1b1b1b;
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

            &:hover {
                filter: grayscale(0%) brightness(1);
            }
        }

    }
}

.itemWrap {
    position: fixed;
    top: 0;
    left: 0;
    z-index: 50;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .8);

    .close{
       
    }

    .itemBg {
        position: fixed;
        top: 50%;
        left: 50%;
        z-index: 50;
        transform: translate(-50%,-50%);
        background-color: #fff;
        width: 60%;
        height: 80%;
    }
}
</style>

<script>

export default {
    data() {
        return {
            open: false,
            list: [
                {
                    name: '黑色契約Ｍ-事前預約',
                    id: new Date(2024, 4, 10).getTime(),
                    date: '2024年4月10日',
                    link: 'https://cbm.digeam.com/prereg',
                    skill: 'Vue3,laravel10,webpack,swiper,aos,axios,rwd',
                    respon: 'frontEnd',
                    thumbnail: '/img/list/list1.jpg',
                    info: '',
                },
                {
                    name: 'Nage-賽季服火爆登場',
                    id: new Date(2024, 1, 11).getTime(),
                    date: '2024年1月11日',
                    link: 'https://nage.digeam.com/event/20240111/',
                    skill: 'Vue3,swiper,aos,axios,rwd',
                    respon: 'FrontEnd',
                    thumbnail: '/img/list/list2.jpg',
                    info: '',
                },
                {
                    name: '小狗英雄-事前預約',
                    id: new Date(2024, 1, 24).getTime(),
                    date: '2024年1月24日',
                    link: '',
                    skill: 'HeidiSQL,laravel8',
                    respon: 'BackEnd',
                    thumbnail: '/img/list/list8.jpg',
                    info: '',
                },
                {
                    name: '仙俠世界貳-網頁商城',
                    id: new Date(2023, 12, 21).getTime(),
                    date: '2023年12月21日',
                    link: 'https://xx2.digeam.com/webmall',
                    skill: 'Vue3,swiper,axios',
                    respon: 'Both',
                    thumbnail: '/img/list/list4.jpg',
                    info: '',
                },
                {
                    name: '絲路紀元-4週年慶典',
                    id: new Date(2023, 12, 12).getTime(),
                    date: '2023年12月12日',
                    link: 'https://sro.digeam.com/event/20231212/',
                    skill: 'Vue3,axios',
                    respon: 'Both',
                    thumbnail: '/img/list/list5.jpg',
                    info: '',
                },
                {
                    name: '黑色契約-事前預約',
                    id: new Date(2023, 3, 28).getTime(),
                    date: '2023年3月28日',
                    link: 'https://rco.digeam.com/prereg',
                    skill: 'jquery,axios',
                    respon: 'FrontEnd',
                    thumbnail: '/img/list/list9.jpg',
                    info: '',
                },
                {
                    name: '赤壁-事前預約（神機鏡）',
                    id: new Date(2023, 3, 28).getTime(),
                    date: '2023年3月28日',
                    link: 'https://rco.digeam.com/prereg',
                    skill: 'jquery,axios',
                    respon: 'FrontEnd',
                    thumbnail: '/img/list/list6.jpg',
                    info: '',
                },
                {
                    name: '夢想飛飛-第二屆夢想設計大賞',
                    id: new Date(2022, 12, 21).getTime(),
                    date: '2022年12月21日',
                    link: 'https://flyff.digeam.com/event/20221221/',
                    skill: 'jquery,axios',
                    respon: 'FrontEnd',
                    thumbnail: '/img/list/list7.jpg',
                    info: '',
                },
            ],
            currentIndex: null
        }
    },
    methods: {
        openItem(idx) {
            this.currentIndex = idx;
            this.open = true;        
        }
    }
}

</script>