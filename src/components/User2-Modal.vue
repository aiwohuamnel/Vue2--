<template>
    <div>
        <modal-demo event-name="btn-stage-2">
            <template v-slot:header><div class="header-text">模态框测试复用组件</div></template>
            <template v-slot:content>内容2</template>
            <template v-slot:footer>联系我们2</template>
        </modal-demo>
        <button class="btn1" @click="setbtn2">弹出组件2</button>
    </div>
</template>

<script>
import ModalDemo from './Modal-demo.vue';

export default {
    name: "User2-Modal",
    components: {
        ModalDemo
    },
    methods: {
        setbtn2() {
            this.$root.$emit("btn-stage-2", true);
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