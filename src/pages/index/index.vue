<template>
  <div class="container" @click="clickHandle('test click', $event)">
    <swiper :indicator-dots="indicatorDots" class = "swiper" :current = "currentIndex" @change="handleChange">
        <swiper-item v-for = "(item,index) in list" :item-id ="item.id" :key = "item.id">
            <div class = "inner">
                <image :src="item.url" class="slide-image" />
                <div class= "bg"></div>
                <div class = "content">
                    <div class = "title">{{item.content}}</div>
                    <div class = "text">{{item.text}}</div>
                </div>
            </div>
        </swiper-item>
    </swiper>
</div>
</template>

<script>
export default {
    data() {
        return {
            currentIndex: 0,
            list: [
                {
                    url: '/static/img/16.jpeg',
                    content: '忘了是怎么开始，也许就是对你有一种感觉~',
                    text:
                        '那年18，退去初中的幼稚，在大学相遇，一句好久不见，你已经偷走了我的影子。',
                },
                { url: '/static/img/2.jpeg', content: '希望你能快乐，如果我们能在一起该多好' },
                {
                    url: '/static/img/17.jpeg',
                    content: '可是我却只敢在你看不见的地方自嘲',
                    text: '只要我敢不懦弱，凭什么我们要错过。',
                },
                {
                    url: '/static/img/3.jpeg',
                    content: '偶然还是天意',
                    text: '如果这只小鸡是你，我可以养到地老天荒，不离不弃。',
                },
                {
                    url: '/static/img/4.jpeg',
                    content: '那些花儿',
                    text: '你喜欢养花，可你自己也是需要呵护的花儿啊',
                },
                {
                    url: '/static/img/5.jpeg',
                    content: '一起游戏',
                    text: '即使你曾经那么菜，我还是觉得和你一起掉分才是最快乐的事。',
                },
                {
                    url: '/static/img/7.jpeg',
                    content: '一起学习',
                    text:
                        '很高兴能和你每天分享打卡，我们也一直走在进步的路上。加油！六级再不过，这个锅我不背~',
                },
                {
                    url: '/static/img/8.jpeg',
                    text:
                        '我不知道你发这条状态的时候，心里的他是谁，但我现在想到的人 是你。我可以。。。你能不能。。。',
                },
                {
                    url: '/static/img/1.jpeg',
                    text:
                        '有时候也会不自觉的暗示你一下，你的回复总是让我猜不透，影子还在，可我希望影子永远在你那啊。',
                },
                {
                    url: '/static/img/9.jpeg',
                    text:
                        '在这夜深人静的520，我想说爱你，但太轻浮，想说喜欢你，但是太幼稚，所以，下面的话都是我想对你说的，还有，I Miss You！',
                },
                { url: '/static/img/10.jpeg', text: '' },
                { url: '/static/img/11.jpeg', text: '' },
                { url: '/static/img/12.jpeg', text: '' },
                { url: '/static/img/13.jpeg', text: '' },
                { url: '/static/img/14.jpeg', text: '' },
                {
                    url: '/static/img/15.jpeg',
                    text: '没有了，只是希望你看到了能够高兴，happy 520~',
                },
            ],
        };
    },

    components: {},
    methods: {
        clickHandle(msg, event) {
            console.log(msg);
        },
        handleChange() {},
    },

    mounted() {},
    onShow() {
        const innerAudioContext = wx.createInnerAudioContext();

        innerAudioContext.src =
            'https://media-audio1.baydn.com/storage_media_audio/vryjyo/1e6389b7e198fbe9bbcdfacff4bd36d0.da69c948d17a754b6dc43f6b8fcedfb4.mp3';
        innerAudioContext.loop = true;
        innerAudioContext.play();
        this.currentIndex = 0;
    },
    onShareAppMessage() {
        return {
            title: '陪伴是最长情的告白，520，a gift for you',
            path: `/pages/index/main`,
        };
    },
};
</script>

<style lang = "less" scoped>
.container {
    .swiper {
        width: 100%;
        height: 100%;
    }
    .inner {
        width: 100%;
        height: 100%;
        position: absolute;

        .slide-image {
            position: absolute;
            width: 100%;
            height: 100%;
        }
        .bg {
            position: absolute;
            bottom: 0;
            width: 100%;
            box-sizing: border-box;
            height: 324px;
            opacity: 0.69;
            background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0), #000000);
        }
        .content {
            position: absolute;
            bottom: 0;
            width: 100%;
            box-sizing: border-box;
            height: 324px;
            padding: 15px 15px 20px 15px;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            & > div {
                margin: 10px 0;
            }
            .title {
                font-family: HelveticaNeue;
                font-size: 16px;
                font-weight: 500;
                line-height: 1.25;
                text-align: justify;
                color: #eeeeee;
                text-shadow: 0 2px 6px rgba(0, 0, 0, 0.5);
            }
            .text {
                font-size: 14px;
                text-align: justify;
                color: #cccccc;
                text-shadow: 0 2px 6px rgba(0, 0, 0, 0.5);
            }
        }
    }

}
</style>
