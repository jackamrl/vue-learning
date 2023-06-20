<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>default content</slot>
      <div class="actions">
        <slot name="links"> </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style scooped lang="scss">
.backdrop {
  top: 0;
  left: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;

  .modal {
    width: 500px;
    padding: 20px;
    margin: 100px auto;
    background: #ffffff;
    border-radius: 10px;

    h1 {
      color: rgb(112, 13, 143);
      border: none;
      padding: 0;
      font-weight: 700;
      text-align: center;
      margin: 10px;
    }

    p {
      text-align: center;
    }
    .actions {
      text-align: center;
      margin: 30px 0 10px 0;

      a {
        color: #333;
        padding: 8px;
        border: 1px solid #eee;
        border-radius: 4px;
        text-decoration: none;
        margin: 10px;
      }
    }
  }

  .modal.sale {
    background: #ca3636;
    color: #fff;

    h1 {
      color: #fff;
    }
    .actions {
      a {
        color: #fff;
        border: 1px solid #fff;
      }
    }
  }
}
</style>
