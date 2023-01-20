<template>
  <section>
    <div>
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
            <button type="submit" value="Send message">Submit</button>
          </div>
        </div>
      </form>
    </div>
  </section>
</template>

<style scoped>
.feedback-form {
  margin: 40px 40px;
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
