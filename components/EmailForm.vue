<script setup lang="ts">

interface FormShape {
  form: string;
  name: string | undefined;
  email: string | undefined;
  message: string | undefined;
}

const Form : FormShape = reactive({
    form: '#contact',
    name: '',
    email: '',
    message: ''
    });

const handleSubmit = () => {
const formData:any = new FormData();
formData.append('name', Form.name);
formData.append('email', Form.email);
formData.append('message', Form.message);


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


<form id="contact" name="contact" method="POST" data-netlify-honeypot="bot-field" data-netlify="true">
    <input type="hidden" value="contact" name="contact" />
    <Transition appear class="delay-16">
  <p>
    <label for="name">Name </label>
    <input id="name" type="text" name="name" placeholder="Name" v-model="Form.name"/>
  </p>
</Transition>
<Transition appear class="delay-17">

  <p>
    <label for="email">Email </label>
    <input id="email" type="text" name="email" placeholder="Email"/>
  </p>
</Transition>
  <Transition appear class="delay-18">

  <p>
    <label for="message">Message </label>
    <textarea id="message" name="message" placeholder="Drop me a note"></textarea>
  </p>
</Transition>
<Transition appear class="delay-19">

  <p>
    <input type="submit" value="Submit" @click.prevent="handleSubmit">
  </p>
  </Transition>
</form>
</template>

<style scoped lang="scss">


label {
    display:none;
}

form {
    /* background-color: var(--color-glowing-lantern); */
    padding: 0 0px;
}

input[type='text'], textarea {
    background-color: var(--color-trapped-darkness);
    border: 3px solid var(--color-maniac-mansion);
    color: var(--color-old-lace);
    font-family: 'Henderson Slab', serif;
    font-size: 1.2rem;
    padding: 10px;
    width: 100%;
    
}

textarea {
  resize: none;
}

.v-enter-active {
  transition: opacity 0.5s ease, transform 0.5s ease;
}
.v-enter-from {
  opacity: 0;
  transform: translateY(100px);
}



.delay-16 {
  transition-delay: 1.6s;
}

.delay-17 {
  transition-delay: 1.7s;
}

.delay-18 {
  transition-delay: 1.8s;
}

.delay-19 {
  transition-delay: 1.9s;
}
</style>