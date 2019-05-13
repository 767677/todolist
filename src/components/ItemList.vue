<template>
  <div>
    <div>TodoList</div>
<div style="float: right">完了済み</div>
      <p style="text-align: left">未完</p>
    <div v-for="item in items" :key="item.name">
      <div class="item">
        <div v-if="item.price== 1" style="text-align: left">
          <div class="name">名前: {{ item.name }}</div>
          <button @click="item.price=-item.price">完了済みに変更</button>
          <br>
        </div>
        <div v-if="item.price== -1" style="text-align: right">
         <div class="name">名前: {{ item.name }}</div>
        <button @click="item.price=-item.price">未完に変更</button>
        <br>
        </div>
      </div>
     </div>
     <br>
    <div>
      <label>
        名前
        <input type="text" v-model="newItemName">
      </label>
      <button @click="addItem">追加</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data() {
    return {
      items: [{ name: "example", price: 1 }, { name: "example2", price: 1 }],
      newItemName: "",
      newItemPrice: 1
    };
  },
  methods: {
    addItem() {
      this.items.push({ name: this.newItemName, price: this.newItemPrice });
    }
  }
  
};
</script>