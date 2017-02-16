<template>
  <SwipeView :bar="false" :bt="true" text="Daily Challenge">
    <div class="view v1">
      <Christmas></Christmas>
    </div>
    <div class="view v2">

    </div>
    <div class="view v3">

    </div>
  </SwipeView>
</template>

<script>
import SwipeView from './SwipeView';
import Christmas from './Index/Christmas';

export default {
  components: { SwipeView, Christmas },
};
</script>

<style scoped>

.v1 {
  background-color: #1B2B2F;
}

.v2 {
  background-color: #f00;
}

.v3 {
  background-color: #ff0;
}

</style>

