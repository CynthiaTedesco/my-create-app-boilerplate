<template>
  <ul class="navbar-nav">
    <li class="nav-item" @click="$emit('toggle')">
      <a
        class="btn btn-menu c-button"
        data-offcanvas-trigger="off-canvas"
        role="button"
        aria-controls="off-canvas"
        aria-expanded="false"
      >
        <span class="c-button__text">Menu</span>
      </a>
    </li>
  </ul>

</template>

<style lang="scss" scoped>
@import "~assets/styles/common.scss";

.nav-item {
  display: flex;
  box-align: center;
  align-items: center;
  cursor: pointer;

  .btn-menu {
    font-size: 30px;
  }
}

.btn-menu {
  position: relative;
  text-indent: -9999px;
  overflow: hidden;
  cursor: pointer;
  outline: 0;
  margin: 0;
  padding: 0;
  border: none;
  height: 38px;
  width: 30px;

  %css-thin-line {
    display: block;
    content: " ";
    position: absolute;
    left: 0;
    width: 30px;
    height: 2px;
    background-color: $dark;
  }

  :before {
    @extend %css-thin-line;
    top: 12px;
  }

  :after{
    @extend %css-thin-line;
    top: 24px;
  }
}
</style>
