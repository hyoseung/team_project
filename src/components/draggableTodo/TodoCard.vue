<template>
  <div class="list-card">
    <div class="list-card-title" @click="showDetailCard">{{todoCard.title}}</div>
    <span class="remove-card-btn" @click="removeCard"><i class="fas fa-trash-alt"></i></span>
  </div>
</template>

<script>
export default {
  props: ['todoCard'],
  methods: {
    removeCard() {
      this.$emit('remove', this.todoCard);
    },
    showDetailCard() {
      this.$emit('show', this.todoCard);
    }
  }
}
</script>

<style scoped>
.list-card {
  background-color: #fff;
  border-radius: 3px;
  box-shadow: 0 1px 0 rgba(9,30,66,.25);
  cursor: pointer;
  display: block;
  margin-bottom: 8px;
  max-width: 300px;
  min-height: 20px;
  position: relative;
  text-decoration: none;
  z-index: 0;
  cursor: pointer;
}

.remove-card-btn {
  opacity: .5;
  padding: 4px;
  position: absolute;
  right: 2px;
  top: 2px;
  z-index: 20px;
  cursor: pointer;
}
.list-card-title {
  overflow: hidden;
  padding: 6px 8px 2px;
  position: relative;
  z-index: 10;

  text-overflow:ellipsis;
  white-space:nowrap;
  word-wrap:normal;
  width:260px;
  overflow:hidden;
}
</style>