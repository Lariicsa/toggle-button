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
            :index="index"
          >
            <ToggleButton
              :item="character"
              :defaultState="false"
              :id="index.toString()"
              @OnChange="AddTofavs()"
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
  },

  methods: {
    AddTofavs() {
      this.$emit("AddTofavs")
    }
  }
};
</script>
