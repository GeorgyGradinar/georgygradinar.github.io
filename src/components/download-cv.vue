<template>
  <button class="download-button">
    <div class="docs">
      <svg class="css-i6dzq1" stroke-linejoin="round" stroke-linecap="round" fill="none" stroke-width="2"
           stroke="currentColor" height="20" width="20" viewBox="0 0 24 24">
        <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
        <polyline points="14 2 14 8 20 8"></polyline>
        <line y2="13" x2="8" y1="13" x1="16"></line>
        <line y2="17" x2="8" y1="17" x1="16"></line>
        <polyline points="10 9 9 9 8 9"></polyline>
      </svg>
      Doc CV
    </div>

    <a class="download" href="../assets/docs/file.pdf" download>
      <svg class="css-i6dzq1" stroke-linejoin="round" stroke-linecap="round" fill="none" stroke-width="2"
           stroke="currentColor" height="24" width="24" viewBox="0 0 24 24">
        <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
        <polyline points="7 10 12 15 17 10"></polyline>
        <line y2="3" x2="12" y1="15" x1="12"></line>
      </svg>
    </a>
  </button>

</template>

<script>

export default {
  name: "download-cv",

  data() {
    return {}
  },

  methods: {}
}
</script>

<style scoped>

.download-button {
  position: relative;
  border-width: 0;
  color: var(--color);
  font-size: 15px;
  font-weight: 600;
  border-radius: 4px;
  z-index: 1;
  margin-bottom: 50px;
  box-shadow: var(--box-shadow);
}

.download-button .docs {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  min-height: 40px;
  padding: 0 10px;
  border-radius: 4px;
  z-index: 1;
  background-color: var(--background);
  transition: all .5s cubic-bezier(0.77, 0, 0.175, 1);
  cursor: pointer;
}

.download {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  max-width: 90%;
  margin: 0 auto;
  z-index: -1;
  border-radius: 4px;
  transform: translateY(0%);
  background-color: var(--background);
  box-shadow: var(--box-shadow);
  border: solid 1px #2F3E46;
  transition: all .5s cubic-bezier(0.77, 0, 0.175, 1);
}

.download,
.download svg,
.download svg path,
.download svg polyline,
.download svg line {
  cursor: pointer;
}

.download-button:hover .download {
  transform: translateY(100%);
}

.download svg polyline, .download svg line {
  animation: docs 1s infinite;
}

.css-i6dzq1 {
  background: transparent;
}

@keyframes docs {
  0% {
    transform: translateY(0%);
  }

  50% {
    transform: translateY(-15%);
  }

  100% {
    transform: translateY(0%);
  }
}

</style>
