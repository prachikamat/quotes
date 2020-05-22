<template>
 <div class="com-sm-6 col-md-4 col-lg-3">
      <div class="panel panel-default">
        <div class="panel-body quote">
          <slot></slot>
        </div>
      </div>
  </div>
</template>

<script>
export default {
}
</script>

<style>

  .panel-body {
        font-family: 'Arizonia', cursive;
        font-size: 24px;
        color-adjust: #6e6e6e;
  }

  .quote:hover {
        background-color: #e2ccdb8c;
  }

</style>
