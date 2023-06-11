<template>
  <div class="my-section">
    <wwLayout path="cards" direction="row" class="cards">
        <template v-slot="{ item }">
            <wwLayoutItem class="card">
                <wwObject v-bind="item"></wwObject>
            </wwLayoutItem>
        </template>
    </wwLayout>
</div>
</template>

<script>
export default {
  props: {
    content: { type: Object, required: true },
  },
  computed: {
    textStyle() {
      return {
        color: this.content.textColor,
      };
    },
  },
};
</script>

<style lang="scss" scoped>
.my-section {
    .cards {
        display: flex;
        justify-content: space-around;
    }
    .card {
        border: 1px solid dashed;
        padding: 4px;
        border-radius: 8px;
        min-width: 100px;
    }
}
</style>
