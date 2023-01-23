<script setup lang="ts">

</script>

<template>


<form name="contact" action="/" data-netlify="true" data-netlify-honeypot="bot-field" hidden>
    <input type="text" name="name" />
    <input type="email" name="email" />
    <textarea name="message"></textarea>
    <input type="submit" value="Submit" />
  </form>

<form name="contact" method="POST" data-netlify-honeypot="bot-field" data-netlify="true">
    <input type="hidden" value="contact" name="contact" />
  <p>
    <label>Your Name: <input type="text" name="name" /></label>
  </p>
  <p>
    <label>Your Email: <input type="email" name="email" /></label>
  </p>
  <p>
    <label>Your Role: <select name="role[]" multiple>
      <option value="leader">Leader</option>
      <option value="follower">Follower</option>
    </select></label>
  </p>
  <p>
    <label>Message: <textarea name="message"></textarea></label>
  </p>
  <p>
    <button type="submit">Send</button>
  </p>
</form>
</template>

<style scoped lang="scss">

</style>