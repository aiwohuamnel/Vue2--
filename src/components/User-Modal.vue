<template>
    <div>
        <modal-demo event-name="btn-stage-1">
            <template v-slot:header><div class="header-text">我是标题</div></template>
            <template v-slot:content>我是内容</template>
            <template v-slot:footer>联系我们</template>
        </modal-demo>
        <button class="btn1" @click="setbtn1">弹出</button>
    </div>
</template>

<script>
import ModalDemo from "./Modal-demo.vue";

export default {
    name: "User-Modal",
    components: {
        ModalDemo
    },
    methods: {
        setbtn1() {
            this.$root.$emit("btn-stage-1", true);
        }
    }
};
</script>

<style lang="css" scoped>
.header-text {
    font-weight: bold;
    font-size: 18px;
}

.btn1 {
    width: 100px;
    height: 40px;
}
</style>