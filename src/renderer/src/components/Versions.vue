<script setup lang="ts">
import { reactive } from 'vue';
import isElectron from 'is-electron';

const versions: any = isElectron()
  ? reactive({ ...window.electron.process.versions })
  : '';
</script>

<template>
  <ul class="versions">
    <li class="electron-version">Electron v{{ versions.electron }}</li>
    <li class="chrome-version">Chromium v{{ versions.chrome }}</li>
    <li class="node-version">Node v{{ versions.node }}</li>
    <li class="v8-version">V8 v{{ versions.v8 }}</li>
  </ul>
</template>
