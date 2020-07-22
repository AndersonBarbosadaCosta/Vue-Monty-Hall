<template>
  <div class="door-area">
    <div class="door-frame" :class="{selected : selected && !open}">
      <Gift v-if="open && hasGift" />
    </div>
    <div class="door" @click="selected = !selected" :class="{open:open}">
      <div class="number" :class="{selected}">{{number}}</div>
      <div class="knob" :class="{selected}" @click.stop="open = true"></div>
    </div>
  </div>
</template>

<script>
import Gift from "./Gift";
export default {
  name: "Door",
  components: { Gift },
  props: {
    hasGift: { type: Boolean },
    number: {}
  },
  data: function() {
    return {
      open: false,
      selected: false
    };
  }
};
</script>

<style>
:root {
  --door-border: 5px solid brown;
  --door-selected: 5px solid yellow;
}
.door-area {
  position: relative;
  width: 200px;
  height: 310px;
  border-bottom: 10px solid #aaa;
  margin-bottom: 20px;
  font-size: 3em;
  display: flex;
  justify-content: center;
}
.door-frame {
  position: absolute;
  height: 300px;
  width: 180px;

  border-left: var(--door-border);
  border-top: var(--door-border);
  border-right: var(--door-border);

  display: flex;
  justify-content: center;
  align-items: flex-end;
}

.door {
  position: absolute;
  width: 170px;
  height: 295px;
  display: flex;
  flex-direction: column;
  align-self: flex-start;
  padding: 15px;
  top: 5px;
  background: chocolate;
}

.door > .knob {
  height: 20px;
  width: 20px;
  border-radius: 10px;
  background: brown;

  display: flex;
  justify-content: flex-start;
  flex-direction: column;
  margin-top: 60px;
}
.door > .number {
  display: flex;
  justify-content: center;
}

.door-frame.selected {
  border-top: var(--door-selected);
  border-left: var(--door-selected);
  border-right: var(--door-selected);
}

.door .number.selected {
  color: yellow;
}

.door > .knob.selected {
  background-color: yellow;
}

.door.open {
  background: #0007;
}

.door.open .knob {
  display: none;
}

.door.open .number {
  display: none;
}
</style>