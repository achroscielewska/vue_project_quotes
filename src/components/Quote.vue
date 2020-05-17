<template>
  <div class="col-sm-6 col-md-4">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>
<script></script>
<style lang="scss" scoped>
.panel-body {
  font-family: "Arizonia", cursive;
  font-size: 24px;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: #ffe2e2;
}
</style>
