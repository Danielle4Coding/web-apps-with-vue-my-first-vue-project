<template>
  <div id="flex-wrapper">
    <div id="list-wrapper">
      <h1>TO DO</h1>
      <ul>
        <li v-for="toDo in toDos" :key="toDo.id">
          <input type="checkbox" :name="toDo.id" :id="'todo-' + toDo.id" />
          {{ toDo.description }}
          <label :for="'toDo-' + toDo.id"></label>
        </li>
        <p>{{ newToDo }}</p>
      </ul>
    </div>
    <div id="button-wrapper">
      <form id="form" @submit.prevent="addToDo">
        <br />
        <label for="newToDo">Add <i>TO DO</i></label>
        <br />
        <input v-model="newToDo" type="text" />
        <button v-on:click="addToDo">Add <i>TO DO</i></button>
        <p id="alert"></p>
      </form>

      <!--
      <form id="filter-form">
        <p id="filterTextEl">Filter <i>TO DOS</i></p>
        <input
          type="radio"
          id="filterAll"
          value="all"
          name="filter"
          checked="checked"
        />
        <label for="filterAll">all</label>
        <br />
        <input type="radio" id="filterDone" value="done" name="filter" />
        <label for="filterDone">done</label>
        <br />
        <input type="radio" id="filterOpen" value="open" name="filter" />
        <label for="filterOpen">open</label>
      </form>

      <form id="sort-form">
        <p id="sortTextEl">Sort <i>TO DOS</i></p>
        <input
          type="radio"
          id="sortDefault"
          value="default"
          name="sort"
          checked="checked"
        />
        <label for="sortDefault">default</label>
        <br />
        <input type="radio" id="sortDone" value="done" name="sort" />
        <label for="sortDone">done</label>
        <br />
        <input type="radio" id="sortOpen" value="open" name="sort" />
        <label for="sortOpen">open</label>
      </form>
      <br />

      <button id="removeBtn">Remove done <i>TO DOS</i></button>
      <br />
      <br />
      <button id="clearBtn">Clear List</button>
    --></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newToDo: "",
      toDos: [
        { id: 1, description: "Learn HTML", done: false },
        { id: 2, description: "Learn CSS", done: true },
      ],
    };
  },
  methods: {
    addToDo() {
      this.toDos.push(this.newToDo).trim;
      this.newToDo = "";
      console.log(this.toDos);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  background-color: #45818e;
  padding: 20px;
}

#flex-wrapper {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  gap: 10px;
}

#button-wrapper {
  margin: 2% auto;
  padding: 20px;
  border: 1px solid #eeeeee;
  border-radius: 10px;

  font-family: Ubuntu;
  font-size: 20px;

  background-color: #f1f8f7;

  height: max-height;
  min-height: 680px;
}
#list-wrapper {
  border: 1px solid #eeeeee;
  border-radius: 10px;
  box-shadow: 1px 1px 0 #dddddd;
  display: block;
  font-family: "Bradley Hand";
  font-size: 22px;
  color: #111199;
  line-height: 50px;
  margin: 2% auto;
  padding: 11px 20px 0 70px;
  resize: none;
  height: max-height;
  min-height: 680px;
  width: 530px;

  background-image: -moz-linear-gradient(top, white, white 49px, #f1f8f7 0px),
    -moz-radial-gradient(4% 50%, circle closest-corner, #f5f5f5, #f5f5f5 39%, transparent
          0%),
    -moz-radial-gradient(3.9% 46%, circle closest-corner, #cccccc, #cccccc 43.5%, transparent
          0%);
  background-image: -webkit-linear-gradient(top, white, white 49px, #e7eff8 0);
  -webkit-background-size: 100% 50px;
  background-size: 100% 50px;
}
ul {
  list-style: none;
  margin-top: -20px;
  margin-left: -50px;
}

ul input {
  width: 27.5px;
  height: 27.5px;
}

ul label {
  margin-left: 20px;
}

button,
input {
  font-size: 20px;
}

h1 {
  margin-top: -10px;
  margin-left: 40px;
  text-decoration: underline;
}

.description--strikeThrough {
  text-decoration: line-through;
}
</style>
