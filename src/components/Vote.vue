<template>
  <div class="buttons">
    <button v-for="(emoticon, index) in emoticons"
      :key="index"
      :id="emoticon"
      :value="emoticon"
      :disabled="isDisable"
      @click="vote"
      class="btn-emoticon">
    </button>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import Moment from "moment";

export default {
  name: "Vote",
  components: {},
  data: function() {
    return {
      emoticons: [
        'very-bad',
        'bad',
        'ok',
        'good',
        'very-good'
      ],
      isDisable: false
    }
  },
  methods: {
    vote(e) {
      this.isDisable =  true;
      let voted = e.target.value;
      let keyStorage = Moment().format('YYYYMMDDhmmss');
      let created_at = Moment().format('YYYY-MM-DD h:mm:ss');
      
      const data = {
        vote: voted,
        created_at: created_at
      }

      let jsonToString = JSON.stringify(data);
      
      localStorage.setItem(keyStorage, jsonToString);
    }
  }
};
</script>

<style>
  .button {
    display: flex;
  }

  .btn-emoticon {
    background: url('~@/assets/emoticon.png');
    width: 101px;
    height: 100px;
    border: none;
    margin: 0 10px;
    outline: none;
    cursor: pointer;
  }

  #very-bad {
    background-position: 0 0;
  }

  #very-bad:hover {
    background-position: 0 -100px;
  }

  #very-bad:active {
    background-position: 0 -200px;
  }

  #bad {
    background-position: -101px 0;
  }

  #bad:hover {
    background-position: -101px -100px;
  }

  #bad:active {
    background-position: -101px -200px;
  }

  #ok {
    background-position: -202px 0;
  }

  #ok:hover {
    background-position: -202px -100px;
  }

  #ok:active {
    background-position: -202px -200px;
  }

  #good {
    background-position: -303px 0;
  }

  #good:hover {
    background-position: -303px -100px;
  }

  #good:active {
    background-position: -303px -200px;
  }

  #very-good {
    background-position: -404px 0;
  }

  #very-good:hover {
    background-position: -404px -100px;
  }

  #very-good:active {
    background-position: -404px -200px;
  }
</style>