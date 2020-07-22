<template>
  <div class="gift">
    <div class="gift-top"></div>
    <div class="gift-body"></div>
    <div class="gift-tie-1"></div>
    <div class="gift-tie-2"></div>
  </div>
</template>

<script>
export default {
  name: "Gift"
};
</script>

<style>
.gift {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 10;
}

.gift-top {
  width: 90px;
  height: 25px;
  background: chartreuse;
}

.gift-body {
  width: 80px;
  height: 60px;
  background: rgb(0, 255, 98);
}

.gift-tie-1 {
  position: absolute;
  height: 85px;
  width: 15px;
  background: red;
}

.gift-tie-2 {
  position: absolute;
  top: 40px;
  height: 15px;
  width: 80px;
  background: red;
}
</style>