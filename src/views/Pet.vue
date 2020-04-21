<template>
    <div>
        <h1>{{displayAnimal.name}}({{$route.params.species}})</h1>
        <p>Breed : {{displayAnimal.breed}}</p>
        <p>Genfer: {{displayAnimal.gender}}</p>
    </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  data () {
    return {
      displayAnimal: {}
    }
  },
  computed: {
    ...mapState(['dogs', 'cats'])
  },
  mounted () {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.displayAnimal = animal
  }
}
</script>
