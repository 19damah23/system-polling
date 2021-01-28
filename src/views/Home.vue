<template>
  <div class="container">
    <section class="vote">
      <h3 class="give-your-vote">Give your vote of our services</h3>

      <div class="emoticons">
        //Ini akan menjadi element vote
      </div>
    </section>

    <section class="finish">
      <h4>Thank's for your vote</h4>
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {}
};
</script>

<style>
  .container {
    display: flex;
    flex-wrap: wrap;
    height: 100vh;
    align-items: center;
  }

  section {
    width: 100%;
  }
</style>