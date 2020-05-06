<template>
  <view class="container">
    <status-bar background-color="grey" bar-style="light-content" />
    <text class="text-color-primary">{{ message }}</text>
    <button v-bind:title="message" v-on:press="handleBtnPress"/>
    <switch v-model="switchVal" />
    <todo-item class="text-container" v-for="todo in todos"
      v-bind:key="todo.id"
      v-bind:item="todo"
    />
  </view>
</template>

<script type="text/javascript">
import TodoItem from './components/todoItem.vue';

export default {
  components: { TodoItem },

  data() {
    return {
      message: 'Ahoj svet',
      switchVal: false,
      todos: [
        { id: 1, text: 'Learn JavaScript' },
        { id: 2, text: 'Learn Vue' },
        { id: 3, text: 'Build something awesome' },
      ],
    };
  },

  methods: {
    handleBtnPress() {
      alert('Btn Press.');
    },
  },
}
</script>

<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-container {
  color: blue;
  padding: 2;
  font-size: 22;
}
.text-input-container {
  width: 300;
  height: 40;
  font-size: 22;
  border-color: gray;
}
.text-color-primary {
  color: blue;
  font-size: 30;
}
</style>
