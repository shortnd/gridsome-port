<template>
  <Layout>
    <template slot="page_title">
      Contact
    </template>
    <template slot="sub_title">
      If you want to talk
    </template>
    <template slot="main">
      <h2 class="text-center text-rouge font-sans text-2xl">Contact Me</h2>
      <form name="contact" class="flex flex-col w-100" method="POST" @submit.prevent="handleSubmit" action="/success/" data-netlify="true" data-netlify-honeypot="bot-field">
        <input type="hidden" name="form-name" value="contact">
        <p hidden>
          <label>
            Don't fill this out: <input name="bot-field" />
          </label>
        </p>
        <div class="sender-info">
          <div class="mb-4">
            <label for="name" class="mb-2 font-bold block font-lg text-grey-darker">Name:</label>
            <input class="shadow px-2 py-3 border appearance-none rounded w-full leading-tight focus:outline-none focus:shadow-outline" type="text" v-model="formData.name" id="name" placeholder="Name" required>
          </div>
          <div class="mb-4">
            <label for="email">Email:</label>
            <input type="email" class="shadow px-2 py-3 border appearance-none rounded w-full leading-tight focus:outline-none focus:shadow-outline" v-model="formData.email" id="email" placeholder="Email" required />
          </div>
          <div class="mb-4">
            <label for="message" class="mb-2 font-bold block font-lg text-grey-darker">Message:</label>
            <textarea v-model="formData.message" id="message" class="shadow border appearance-none rounded w-full px-2 py-2 leading-tight resize-none focus:outline-none focus:outline-rouge focus:shadow-outline" placeholder="Enter your message here." col="30" rows="10" required></textarea>
          </div>
          <div class="mb-4">
            <button class="px-3 py-2 bg-rouge border-rouge text-white font-semibold border rounded hover:bg-transparent hover:text-rouge mr-2" type="submit">Submit</button>
            <button class="px-3 py-2 bg-transparent border-rouge text-rouge font-semibold border rounded hover:bg-rouge hover:text-white" type="reset">Reset</button>
          </div>
        </div>
      </form>
    </template>
  </Layout>
</template>

<script>
export default {
  data() {
    return {
      formData: {},
    }
  },
  methods: {
    encode(data) {
      return Object.keys(data)
        .map(key => encodeURIComponent(key) + "=" + encodeURIComponent(data[key]))
        .join('&')
    },
    handleSubmit(e) {
      fetch('/', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/x-www-form-urlencoded'
        },
        body: this.encode({
          'form-name': e.target.getAttribute('name'),
          ...this.formData,
        }),
      })
      .then(() => this.$router.push('/success'))
      .catch(error => alert(error))
    }
  }
}
</script>

<style>

</style>
