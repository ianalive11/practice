<template>
  <div>
      <div class="TodoList">
        <h2>Todo List</h2>
        <div class="input-block">
          <input class="label-input" placeholder="請輸入待辦事項" type="text" v-model="newList">
          <button class="btn-add" @click="add()">新增</button>
        </div>
        <ul class="list">
          <li v-for="(item, i) in defaultList" :key="i" class="item-text" :class="item.isCheck == 1? 'is-checked' :''">
            <input type="checkbox" :checked="item.isCheck" @change="check(item)">
            <span>{{item.content}}</span>
            <button class="btn-del" @click="del(item,i)">刪除</button>
          </li>
        </ul>
      </div>
  </div>
</template>

<script>
import '../scss/ToDoList.scss' 
export default {
  data() {
    return {
      defaultList: [
        {content:'買水果', isCheck: 0},
        {content:'買菜', isCheck: 0}
      ],
      newList: ''
    }
  },
  methods: {
    add() {
      this.defaultList.push({content:this.newList, isCheck: 0})
      this.newList = ''
    },
    check(item) {
      item.isCheck = !item.isCheck
    },
    del(item,i) {
      this.defaultList.splice(i,1)
    }
  },
}
</script>

<style>

</style>