<script setup lang="ts">
// Importing altcha package will introduce a new element <altcha-widget>
import 'altcha';

defineProps<{ msg: string }>()
</script>

<template>
  <h1>{{ msg }}</h1>


  <div class="card">
    <form action="#">
      <fieldset>
        <label>Name:</label>
        <input type="text" name="name" />
      </fieldset>

      <fieldset>
        <label>Message:</label>
        <textarea name="message"></textarea>
      </fieldset>

      <fieldset>
        <!-- Configure your `challengeurl` and remove the `test` attribute, see docs: https://altcha.org/docs/website-integration/#using-altcha-widget -->
        <altcha-widget
          style="--altcha-max-width:100%"
          debug
          test
        ></altcha-widget>
      </fieldset>

      <button type="submit">Submit</button>
    </form>

    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div>

  <p>
    Check out
    <a href="https://vuejs.org/guide/quick-start.html#local" target="_blank"
      >create-vue</a
    >, the official Vue + Vite starter
  </p>
  <p>
    Learn more about IDE Support for Vue in the
    <a
      href="https://vuejs.org/guide/scaling-up/tooling.html#ide-support"
      target="_blank"
      >Vue Docs Scaling up Guide</a
    >.
  </p>
  <p class="read-the-docs">Click on the Vite and Vue logos to learn more</p>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
