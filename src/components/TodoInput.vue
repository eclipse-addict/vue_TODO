<template>
  <div class="inputBox shadow">
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
    <!-- <button v-on:click="addTodo">add</button> -->
    <span class="addContainer" v-on:click="addTodo">
      <i class="fa-solid fa-plus addBtn"></i>
    </span>
    <AlertModal v-if="showModal" @close="showModal = false">
      <!-- slot-> 다른 컴포넌트를 본 컴포넌트에 등록해서 사용할 때, 모달 쪽에서 등록된 템플릿 형태를 재정의 할 때 사용할 수 있다. -->
      <h3 slot="header"> 
        Warnning !!!
        <i class="fa-regular fa-circle-xmark closeModal" @click="showModal = false"></i>
      </h3>
      <h4 slot="body">추가 할 내용을 입력해주세요.</h4>
      <h5 slot="footer">Copyright@</h5>
    </AlertModal>
  </div>
</template>

<script>
import AlertModal from './common/AlertModal.vue'
export default {
  data() {
    return {
      newTodoItem :"",
      showModal: false
    }
  },
  methods:  {
    addTodo() {
      if (this.newTodoItem !== ''){
        // this.$emit('addTodoItme', this.newTodoItem)
        this.$store.commit('addOneItem', this.newTodoItem);
      // this.newTodoItem = '';
        this.cleaerInput();
      }else{
        //alert('type Something') // browser 내장 alert 창
        this.showModal = !this.showModal 
      }
    },
    // 기능의 분리. 
    cleaerInput() {
      this.newTodoItem = '';
    },
  },
  components: {
   AlertModal,
  }
}
</script>

<style scoped>
input:focus {
  outline: none;
}
.inputBox {
   background: white;
   height: 50px;
   line-height: 50px;
   border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}

.addContainer {
  float: right;
  background: linear-gradient(to right, #6478FB, #8763FB);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}

.addBtn {
  color: white;
  vertical-align: middle;
}
.closeModal{
  color: #42b983;
}

</style>