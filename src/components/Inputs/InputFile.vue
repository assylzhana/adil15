<template>
  <div class="file-input-container">
    <div class="input-container">
      <label for="File" class="input-label">File:</label>
      <div class="input-wrapper">
        <input
          name="File"
          id="fileArea"
          v-model="selectedFileName"
          placeholder="Selected File Name"
          readonly
          class="selected-file"
        />
        <button @click="selectFile" class="upload-button">
          📄
        </button>
      </div>
      <input
        type="file"
        id="fileInput"
        ref="fileInput"
        @change="handleFileChange"
        style="display: none; position: relative;"
      />
      <div class="error" :class="{ 'error-visible': errorVisible }">
        {{ errorMessage }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fileSelected: false,
      errorVisible: false,
      errorMessage: 'Invalid file type.',
      selectedFileName: '',
    };
  },
  methods: {
    selectFile() {
      this.$refs.fileInput.click();
    },
    handleFileChange() {
      const fileInput = this.$refs.fileInput;
      const selectedFile = fileInput.files[0];

      this.errorVisible = !this.validateFile(selectedFile);
      this.fileSelected = !this.errorVisible;
      this.selectedFileName = selectedFile ? selectedFile.name : '';

      if (!this.errorVisible) {
        this.$emit('file-selected', selectedFile);
      }
    },
    validateFile(file) {
      return file && file.type.includes('image/');
    },
  },
};
</script>

<style scoped>
.file-input-container {
  max-width: 300px;
  margin: 20px auto;
}

.input-container {
  position: relative;
}

.input-label {
  display: block;
  margin-bottom: 5px;
  font-size: 18px;
}

.input-wrapper {
  position: relative;
}

.selected-file {
  width: 100%; 
  padding: 10px;
  font-size: 16px;
  border: 2px solid #ccc;
  border-radius: 5px;
  transition: border-color 0.3s ease-out;
}

.upload-button {
  position: absolute;
  right: 5px;
  top: 50%;
  font-size: 25px;
  margin-right: -20px;
  transform: translateY(-50%);
  cursor: pointer;
  background: none;
  border: none;
}

.error {
  color: rgb(255, 47, 47);
  font-weight: bold;
  font-size: 13px;
  position: absolute;
  bottom: -20px;
  opacity: 0;
  transition: top 0.3s ease-out, opacity 0.3s ease-out;
  z-index: 1;
}

.error-visible {
  opacity: 1;
}
</style>
