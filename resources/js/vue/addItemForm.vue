<template>
  <div class="addItem">
    <input type="text" v-model="item.name" />
    <font-awesome-icon
      icon="plus-square"
      @click="addItem()"
      :class="[item.name ? 'active' : 'inactive', 'plus']" 
    />
      <!-- Where-ever it's inactive or not we're going to use the plus -->
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      item: {
        name: "",
      },
    };
  },

  methods: {
    addItem() {
      if (this.item == "") {
        return;
      }

      axios
        .post("api/item/store", {
          item: this.item,
        })
        .then((response) => {
          if (response.status == 201) {
            this.item.name = ""; // Clears entry after it has been added.
            this.$emit("reloadlist");
          }
        })
        .catch((error) => {
          alert(error);
        });
    },
  },
};
</script>

<style scoped>
.addItem {
  display: flex;
  justify-content: center;
  align-items: center;
}

input {
  background: #f7f7f7;
  border: 0px;
  outline: none;
  padding: 5px;
  margin-right: 10px;
  width: 100px;
}

.plus {
  font-size: 20px;
}

.active {
  color: #00ce25;
}

.inactive {
  color: #999999;
}
</style>