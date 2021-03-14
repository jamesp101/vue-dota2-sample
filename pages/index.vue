<template>
  <div class="columns is-fluid is-multiline">
    <HeroCard
      v-for="hero in heroes"
      :key="heroes"
      :heroName="hero.localized_name"
      :primaryAttribute="hero.primary_attr"
      :attackType="hero.attack_type"
      :roles="hero.roles"
    ></HeroCard>
  </div>
</template>

<script>
import HeroCard from '~/components/HeroCard'
import axios from 'axios'

export default {
  name: 'HomePage',
  components: {
    HeroCard,
  },

  data() {
    return {
      heroes: [],
    }
  },

  created() {
    axios.get(`https://api.opendota.com/api/heroes`).then((response) => {
      this.heroes = response.data
    })
  },
}
</script>
