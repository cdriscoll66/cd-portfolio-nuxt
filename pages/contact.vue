<script setup>

const handleSubmit = () => {
    console.log('submitting form');
const formData = new FormData();
formData.append = ('form-name', 'contact-form'),
formData.append('name', 'it worked');
// formData.append('email', Form.email);
// formData.append('message', Form.message);

 
    fetch("/", {
    method: "POST",
    headers: { "Content-Type": "application/x-www-form-urlencoded" },
    body: new URLSearchParams(formData).toString(),
  })
    .then(() => console.log("Form successfully submitted"))
    .catch((error) => alert(error));

}

</script>

<template>
  <section>
    <div class="feedback-form">
      <form
        name="contact-form"
        method="post"
        action="/success/"
        data-netlify="true"
        data-netlify-honeypot="bot-field"
      >
        <div>
          <input type="hidden" name="form-name" value="contact-form" />
          <div>
            <input
              for="name"
              type="text"
              name="name"
              required
              placeholder="Name"
            />
          </div>
          <div>
            <input type="email" name="email" required placeholder="Email" />
          </div>
          <div>
            <textarea name="message" required placeholder="Message"></textarea>
          </div>
          <div>
            <button type="submit" value="Send message" @click.prevent="handleSubmit">Submit</button>
          </div>
        </div>
      </form>
    </div>
  </section>
</template>

<style scoped>
.feedback-form {
  margin: 140px 40px;
  min-width: 250px;
  width: 45%;
}
input,
textarea,
button {
  font-size: inherit;
  margin: 15px 0;
  padding: 12px 20px;
  width: 100%;
}
button {
  background-color: teal;
  border: 1px solid black;
  color: white;
  width: 50%;
}
.hidden {
  clip: rect(0 0 0 0);
  clip-path: inset(50%);
  height: 1px;
  overflow: hidden;
  position: absolute;
  white-space: nowrap;
  width: 1px;
}
</style>
