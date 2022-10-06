<template>
  <!-- <div> -->
  <!-- <div class="d-flex align-items-center justify-space-between"> -->
  <a
    name=""
    id=""
    class="btn btn-link px-1 text-decoration-none text-white btn-block rounded-0 mt-0 mr-2 d-flex flex-column"
    href="#"
    role="button"
  >
    <small class="mb-2">{{ name }}</small>
    <span class="odd">{{ odds }}</span>
  </a>

  <!-- </div> -->
  <!-- </div> -->
</template>

<script>
export default {
  name: 'odds',
  props: {
    odds: {
      required: true,
    },
    active: {
      required: true,
    },
    name: {
      required: false,
    }
  },
}
</script>

<style scoped>
.odd{
  font-size: 18px;
    padding: 5px 15px;
    background: #333;
    border-radius: 5px;
      box-shadow: inset 0.5px 0.5px 2px #636363, 0 2px 4px rgb(26 26 26 / 50%);

}
</style>
