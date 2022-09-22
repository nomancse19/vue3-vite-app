<template>
  <teleport to="#notification">
    <div class="the-notifications">
      {{ text }}
    </div>
  </teleport>
</template>

<script>
export default {
  props: ["text"],
};
</script>

<style>
.the-notifications {
  width: 222px;
  min-height: 22px;
  background-color: #fff;
  color: rgb(255, 24, 174);
  font-weight: bold;
  padding: 15px 7px;
  border: 1px solid gray;
  margin: 22px;
  margin-right: 10px;
  line-height: 1;
  transition: all 0.25s;
  box-shadow: 0 0 8px 2px rgb(0, 0, 0, 0.5);
}

#notification {
  position: fixed;
  top: 0;
  right: 0;
  z-index: -1;
}
</style>
