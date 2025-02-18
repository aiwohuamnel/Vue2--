<template>
  <div class="content">
    <div class="demo"><h1>测试Modal模态框组件</h1>
<user-modal></user-modal>
<user2-modal></user2-modal>

</div>
  </div>

</template>

<script>

import UserModal from "./components/User-Modal.vue";
import User2Modal from "./components/User2-Modal.vue"
  export default {
    data(){
      return{
    flag:false,
    flag2:false
      }
    },

    components:{
      UserModal,
      User2Modal
    
  },
methods:{
  
  setbtn2(){
    this.$root.$emit("btn-stage2",true);
  }
}


  }
</script>

<style lang="css" scoped>
.content{
  width: 800px;
  height: 200px;
  margin: 0 auto;
  border: 1px solid #404040;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.demo{
display: flex;
flex-direction: column;
align-items: center;

}

</style>