<template>
  <div id="app">
    <div class="main-container">
      <div class="select-panel">
        <div>
          <span>Account name</span>
          <select v-model="account">
            <option
              v-for="option in options" :value="option.value" :key="option.value">
              {{option.text}}
            </option>
          </select>
        </div>
        <div>
          <span>Number of feeds</span>
          <select v-model="numberOfFeeds">
            <option
              v-for="number in 15" :value="number" :key="number">
              {{number}}
            </option>
          </select>
        </div>
      </div>
      <Instagram :account = "account" :numberOfFeeds = "numberOfFeeds" />
      </div>
  </div>
</template>

<script>
import Instagram from './components/Instagram.vue';

export default {
  name: 'App',
  components: {
    Instagram,
  },
  data: () => ({
    numberOfFeeds: 15,
    account: '',
    options: [
      { text: 'Please select..', value: '' },
      { text: 'artnightevents', value: 'artnightevents' },
      { text: 'shakenightevents', value: 'shakenightevents' },
      { text: 'plantnightevents', value: 'plantnightevents' },
    ],
  }),
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.main-container {
  width: 80%;
  margin: auto;
}
.select-panel {
  display: flex;
  justify-content: space-between;
}
@media (max-width: 700px) {
  .select-panel{
    flex-direction: column;
    align-items: flex-end;
  }
}
select {
  font-size: 1.1em;
  padding: .3em;
  border-radius: .2em;
  margin: .5em;
}
</style>
