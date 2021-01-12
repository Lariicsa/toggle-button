<template>
  <div id="app" class="space">
    <div class="container">
      <div class="row center">
        <h1>Futurama</h1>
      </div>
      <div class="row center">
        <div class="row between">
          <CardItem
            v-for="(character, index) in characters"
            :character="character"
            :key="index"
            :index="parseInt(index + 1)"
          >
            <ToggleButton
              :item="character"
              labelEnableText="Quit from Favs"
              labelDisableText="Add to Favs"
              :defaultState="false"
            />
          </CardItem>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import store from "@/fakeStore/characters";
import CardItem from "@/components/CardItem";
import ToggleButton from "@/components/ToggleButton";
export default {
  name: "App",
  components: {
    CardItem,
    ToggleButton
  },

  data() {
    return {
      characters: store.characters
    };
  }
};
</script>
