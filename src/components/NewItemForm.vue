<template>
    <div class="add-item">
        <form action="#" method="post" v-on:submit.prevent="submitForm">
            <input type="text" v-model="itemText" placeholder="Добавь новую задачу в список">
        </form>
    </div>
</template>

<script>
export default {
  name: 'NewItemForm',
  data() {
    return {
      itemText: ''
    };
  },
  methods: {
    submitForm() {
      if (this.itemText) {
        this.$store.commit('addItem', {
          text: this.itemText
        });
        this.itemText = '';
      }
    }
  }
};
</script>

<style>
.add-item input {
  outline: none;
  border: 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.5);
  width: 100%;
  transition: all 0.25s;
  background: inherit;
  color: white;
}
.add-item input:focus {
  border-bottom-color: rgba(255, 255, 255, 1);
}
.add-item {
  margin: 30px 0;
}
</style>
© 2021 GitHub, Inc.
