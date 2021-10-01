<template>
      <form>
          <div>
              <input type="text" placeholder="digita il nome del film">
          </div>

          <div>
              <button>Cerca</button>
          </div>
      </form>
  
</template>

<script>
import axios from 'axios';

export default {
    name: "SearchBar",
    data: function(){

    }

}
</script>

<style scoped lang="scss">
@import './style/variables.scss';

</style>