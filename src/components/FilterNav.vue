<template>
  <!---leftside2  v-if="leftsideFunction2"-->
  <aside id="leftside2" class="hide" v-if="leftSideFunction">
    <button v-on:click="leftSideFunction" id="side-bar-btn">SIDE</button>

  <section id="seasons">
    <h1>Filter By Season</h1>
    <ul>
      <li v-for="season in seasons" v-bind:key="season.id">
        <button v-on:click="SearchItemBtn(season.title)">{{season.title}}</button>
      </li>
    </ul>
  </section>
  <section id="locations">
    <h1>Filter By Location</h1>
    <ul>
      <li v-for="location in locations" v-bind:key="location.id">
        <button v-on:click="SearchItemBtn(location.title)">{{location.title}}</button>
      </li>
    </ul>
  </section>
  <section id="prices">
    <h1>Filter By Price</h1>
    <ul>
      <li v-for="price in prices" v-bind:key="price.id">
        <button v-on:click="SearchItemBtn(price.title)">{{price.title}}</button>
      </li>
    </ul>
  </section>
  <section id="ratings">
    <h1>Filter By Rating</h1>
    <ul>
      <li v-for="rating in ratings" v-bind:key="rating.id">
        <button v-on:click="SearchItemBtn(rating.title)">{{rating.title}}</button>
      </li>
    </ul>
  </section>
    <br />
  </aside>
</template>

<script>
export default {
  name: "FilterNav",

  props: ["seasons", "prices", "locations", "ratings"],

  methods: {
    leftSideFunction: function(event) {
      event.preventDefault();

      var el = document.getElementById("leftside2");

      var box = el.getAttribute("class");

      if (box == "hide") {
        el.setAttribute("class", "show");
      } else {
        el.setAttribute("class", "hide");
      }
    },

    SearchItemBtn(item) {
      this.$emit("seasonClick", item);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style lang="scss" >
</style>
