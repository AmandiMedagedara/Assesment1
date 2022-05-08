<template>
  <div class="source-selection">
    <div class="jumbotron">
      <h2>
        <span class="glyphicon glyphicon-list-alt"></span>
        News List
      </h2>
      <h4>Select News source</h4>

      <select class="form-control" v-on:change="sourceChanged">
        <option v-bind:key="source.id" v-for="source in sources">{{source.name}}</option>
      </select>

      <div v-if="source">
        <h6>{{source.description}}</h6>
        <a v-bind:href="source.url" class="btn btn-primary" target="_blank">Go to {{source.name}} website</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['apiKey'],
  data: () => {
    return {
        apiUrl: '',
        sources: [],
        source: ''
    };
  },
  methods: {
    sourceChanged(e) {
      this.sources.some(s => {
        if(s.id === e.target.value) {
          this.source = s;
          return true;
        }
        return false;
      });
      this.$emit('sourceChanged', this.source);
    },
    fetchSources() {
        this.apiUrl = `https://newsapi.org/v2/sources?apiKey=` + this.apiKey
    }
  },
  created() {
    this.fetchSources();
  }
}
</script>

<style scoped>
</style>
