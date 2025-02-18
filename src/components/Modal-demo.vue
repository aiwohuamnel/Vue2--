<template>
    <div class="switch" v-show="flag">
        <div class="content">
            <div class="header">
                <slot name="header" class="header-text"></slot>
                <div class="btn"><button @click="handleClick">X</button></div>
            </div>
            <div class="contents">
                <slot name="content"></slot>
            </div>
            <div class="footer">
                <slot name="footer"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Modal-demo",
    data() {
        return {
            flag: false
        };
    },
    mounted() {
        // 根据传入的事件名监听事件
        this.$root.$on(this.eventName, flag => {
            this.flag = flag;
        });
    },
    beforeDestroy() {
        // 根据传入的事件名移除事件监听
        this.$root.$off(this.eventName);
    },
    props: {
        eventName: {
            type: String,
            required: true
        }
    },
    methods: {
        handleClick() {
            this.flag = false;
        }
    }
};
</script>

<style lang="css" scoped>
.switch {
    position: fixed;
    background-color: rgba(128, 128, 128, 0.5);
    left: 0px;
    right: 0px;
    top: 0px;
    bottom: 0px;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}

.content {
    width: 450px;
    height: 300px;
    display: flex;
    flex-direction: column;
    align-items: center;
    border-radius: 10px;
    background-color: rgb(238, 236, 236);
}

.header {
    display: flex;
    flex-direction: row;
    position: relative;
    width: 100%;
    height: 40px;
    justify-content: center;
    align-items: center;
    border-radius: 10px 10px 0px 0px;
    background-color: aliceblue;
}

.btn {
    position: absolute;
    right: 10px;
    width: 30px;
    height: 30px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
}

.btn button {
    width: 30px;
    height: 30px;
    border-radius: 15px;
    border: 0px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    background-color: rgb(8, 113, 241);
    color: white;
    font-weight: bold;
}

.contents {
    width: 430px;
    height: 200px;
    padding: 10px;
}

.footer {
    width: 450px;
    height: 40px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    background-color: rgb(8, 113, 241);
    color: white;
    font-weight: bold;
    border-radius: 0px 0px 10px 10px;
}
</style>