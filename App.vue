<template>
  <view class="container">
    <status-bar background-color="grey" bar-style="light-content" />
    <text class="text-color-primary">vue-native helloReact</text>
    <touchable-opacity
        v-bind:on-press="handleBtnPress"
        v-bind:style="{ backgroundColor: 'green', padding: 5 }">
      <text v-bind:style="{ color: 'white' }">{{ message }}</text>
    </touchable-opacity>
    <text>{{ fetched }}</text>
    <switch v-model="switchVal" />
    <scroll-view>
      <todo-item class="text-container border" v-for="todo in todos"
        v-bind:key="todo.id"
        v-bind:item="todo"/>
    </scroll-view>
  </view>
</template>

<script type="text/javascript">
import TodoItem from './components/todoItem.vue';

export default {
  components: { TodoItem },

  data() {
    return {
      message: 'Ahoj svet',
      fetched: '',
      switchVal: false,
      todos: [
        { id: 1, title: 'Learn JavaScript' },
        { id: 2, title: 'Learn Vue' },
        { id: 3, title: 'Build something awesome' },
        { id: 4, title: 't4' },
        { id: 5, title: 't5' },
        { id: 6, title: 't6' },
        { id: 7, title: 't7' },
        { id: 8, title: 't8' },
        { id: 9, title: 't9' },
        { id: 10, title: 't10' },
        { id: 11, title: 't11' },
        { id: 12, title: 't12' },
        { id: 13, title: 't13' },
      ],
    };
  },

  methods: {
    handleBtnPress() {
      fetch('https://reactnative.dev/movies.json')
          .then((response) => response.json())
          .then((json) => {
            this.fetched = json.description;
            this.todos = json.movies;
          })
          .catch((error) => {
            console.error(error);
          });
      //alert('Btn Press.');
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
.border {
  border-bottom-width: 1;
  border-color: gray;
  width: 100%;
  padding: 15;
}
</style>
