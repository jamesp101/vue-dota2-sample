<template>
  <div class="column">
    <div class="card hero-card">
      <img src="~/static/antimage.jpg" alt="" class="hero-image" />
      <div class="hero-info">
        <h1 class="hero-name">{{ heroName }}</h1>

        <div class="hero-icons columns row">
          <!-- start: Primary Attribute -->
          <div class="icon" v-if="primaryAttribute == 'str'">
            <img src="~/assets/fist.svg" alt="" class="attribute" />
            <h1 class="icon-description">STR</h1>
          </div>

          <div class="icon" v-else-if="primaryAttribute == 'agi'">
            <img src="~/assets/running.svg" alt="" class="attribute" />
            <h1 class="icon-description">AGI</h1>
          </div>

          <div class="icon" v-else-if="primaryAttribute == 'int'">
            <img src="~/assets/magic-wand.svg" alt="" class="attribute" />
            <h1 class="icon-description">INT</h1>
          </div>
          <!-- end: Primary Attribute -->

          <!-- start: ATTACK TYPE -->
          <div class="icon" v-if="attackType === 'Melee'">
            <img src="~/assets/sword.svg" alt="" class="attribute" />
            <h1 class="icon-description">Melee</h1>
          </div>
          <div class="icon" v-else>
            <img src="~/assets/bow.svg" alt="" class="attribute" />
            <h1 class="icon-description">Ranged</h1>
          </div>

          <!-- end: ATTACT TYPE> -->
        </div>

        <!-- start: ROLES -->
        <div class="hero-icons columns row">
          <div v-for="role in roles">
            <div class="icon" v-if="role === 'Nuker'">
              <img src="~/assets/fire.svg" alt="" class="attribute" />
              <h1 class="icon-description">Nuker</h1>
            </div>
            <div class="icon" v-else-if="role === 'Carry'">
              <img src="~/assets/biceps.svg" alt="" class="attribute" />
              <h1 class="icon-description">Carry</h1>
            </div>
            <div class="icon" v-else-if="role === 'Durable'">
              <img src="~/assets/shield.svg" alt="" class="attribute" />
              <h1 class="icon-description">Durable</h1>
            </div>
            <div class="icon" v-else-if="role === 'Escape'">
              <img src="~/assets/running.svg" alt="" class="attribute" />
              <h1 class="icon-description">Escape</h1>
            </div>
            <div class="icon" v-else-if="role === 'Support'">
              <img src="~/assets/care.svg" alt="" class="attribute" />
              <h1 class="icon-description">Support</h1>
            </div>
            <div class="icon" v-else-if="role === 'Disabler'">
              <img src="~/assets/ray.svg" alt="" class="attribute" />
              <h1 class="icon-description">Disabler</h1>
            </div>
            <div class="icon" v-else-if="role === 'Initiator'">
              <img src="~/assets/shuttle.svg" alt="" class="attribute" />
              <h1 class="icon-description">Initiator</h1>
            </div>
            <div class="icon" v-else-if="role === 'Pusher'">
              <img src="~/assets/shuttle.svg" alt="" class="attribute" />
              <h1 class="icon-description">Pusher</h1>
            </div>
          </div>
        </div>

        <!-- end: ROLES -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HeroCard',

  props: {
    heroName: {
      type: String,
    },
    primaryAttribute: {
      type: String,
    },
    attackType: {
      type: String,
    },
    roles: {
      type: Array,
    },
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Condensed:wght@700&display=swap');
.attribute {
  max-height: 100%;
  color: white;
  margin-left: auto;
  margin-right: auto;
}
.hero-card {
  height: 500px;
  min-width: 300px;
  max-width: 300px;
  position: relative;
}
.hero-image {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 100%;
  z-index: 0;
  object-fit: cover;
}

.hero-info {
  position: absolute;
  z-index: 9999;
  top: 70%;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.3);
}
.hero-name {
  color: white;
  font-size: 1.5rem;
  font-family: 'Roboto Condensed', sans-serif;
  text-transform: uppercase;
  transform: scaleY(1.4);
  white-space: nowrap;
  overflow: hidden;
}
.icon-description {
  text-align: center;
  color: white;
  font-size: 0.65rem;
}
.hero-icons {
  margin-top: 10px;
  display: flex;
  flex-direction: row;
  margin-left: 0.6rem;
}
.hero-info > * {
  margin-left: 1rem;
  margin-right: 1rem;
}
.icon {
  width: 24px;
  height: 40px;
  display: flex;
  flex-direction: column;
  margin-right: 0.8em;
}
.roles: {
  margin-top: 2rem;
}
</style>
