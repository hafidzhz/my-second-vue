<template>
  <section id="user-goals">
    <h2>My course goals</h2>
    <input type="text" v-model="enteredGoal"/>
    <button @click="addGoal">Add Goal</button>
    <p v-if="goals.length === 0">No goals have been added yet - please start adding some!</p>
    <ul v-else>
        <li v-for="(goal, index) in goals" :key="goal" @click="removeGoal(index)">
          <p>{{index+1}}. {{goal}}</p>
          <input type="text" @click.stop/>
        </li>
    </ul>
  </section>
</template>

<script>
export default {
  data () {
    return {
      goals: [],
      enteredGoal: ''
    }
  },
  watch: {

  },
  methods: {
    addGoal () {
      this.goals.push(this.enteredGoal)
    },
    removeGoal (index) {
      this.goals.splice(index, 1)
    }
  }
}
</script>

<style lang="css" scope>
  #user-goals {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}

#user-goals h2 {
  font-size: 2rem;
  border-bottom: 4px solid #ccc;
  color: #1b995e;
  margin: 0 0 1rem 0;
}

#user-goals ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}

#user-goals li {
  margin: 1rem 0;
  font-size: 1.25rem;
  font-weight: bold;
  background-color: #8ddba4;
  padding: 0.5rem;
  color: #1f1f1f;
  border-radius: 25px;
}

#user-goals input {
  font: inherit;
  border: 1px solid #ccc;
}

#user-goals input:focus {
  outline: none;
  border-color: #1b995e;
  background-color: #d7fdeb;
}

#user-goals button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background-color: #ff0077;
  color: white;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}

#user-goals button:hover,
#user-goals button:active {
  background-color: #ec3169;
  border-color: #ec3169;
  box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.26);
}
</style>
