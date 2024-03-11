<template>
  <div class="popup">
    <div class="popup-overlay" @click="closePopup"></div>
    <div class="popup-content">
      <div class="popup-header">
        <h2>{{ title }}</h2>
        <span class="popup-close-btn" @click="closePopup">×</span>
      </div>
      <div class="popup-body">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "Popup Title"
    }
  },
  methods: {
    closePopup() {
      this.$emit("close");
    }
  }
};
</script>

<style scoped>
.popup {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}

.popup-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}

.popup-content {
  background: #fff;
  padding: 20px;
  border-radius: 8px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
}

.popup-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 10px;
}

.popup-header h2 {
  margin: 0;
}

.popup-close-btn {
  cursor: pointer;
}
</style>
