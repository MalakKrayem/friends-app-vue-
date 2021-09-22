<template>
  <div>
    <form @submit.prevent="add">
      <div>
        <label>Name</label>
        <input type="=text" v-model="name" />
      </div>
      <div>
        <label>Phone</label>
        <input type="=tel" v-model="phone" />
      </div>
      <div>
        <label>E-mail</label>
        <input type="=email" v-model="email" />
      </div>
      <div>
        <button>Add Contact</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  emits: ["add-contact"],
  data() {
    return {
      name: "",
      phone: "",
      email: "",
    };
  },
  methods: {
    add() {
      this.$emit("add-contact", this.name, this.phone, this.email);
    },
  },
};
</script>

<style lang="scss" scoped></style>
