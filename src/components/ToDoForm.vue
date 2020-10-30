<template>
  <form @submit.prevent="onSubmit">
    <h2  class="label-wrapper">
      <label for="new-todo-input" class="label__lg">
        What needs to be done?
      </label>
    </h2>
    <input
      type="text"
      id="new-todo-input"
      name="new-todo"
      autocomplete="off"
      v-model.lazy.trim="label"
      class="input__lg"
    />
    <button type="submit" class="btn btn__primary btn__lg">
      Add
    </button>
  </form>
</template>

<script>
export default {
    methods:{
        onSubmit(){
            if(this.label.trim() === ""){              //使用trim删去其输入的字符串中的空格 接下来判断其是否没有输入
                return;
            }
            this.$emit('todo-added', this.label);      //定义了一个名为“todo-added”的事件    通过this访问数据属性，可以通过this.label访问字段的数据
        }
    },
    data(){
        return{
            label:""
        };
    }
}   

</script>

<style>

</style>