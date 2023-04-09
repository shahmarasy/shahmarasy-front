<template>
  <div class="sections mobile">
    <h5 class="title">
      About Me
    </h5>
    <hr class="in_hr">
    <div class="content">
      <table class="w-100">
        <tbody>
          <tr>
            <td class="variables" v-html="content"></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <div class="sections desktop">
    <h5 class="title">
      About Me
    </h5>
    <hr class="in_hr">
    <div class="content">
      <table class="w-100">
        <tbody>
          <tr>
            <td class="variables" v-html="content"></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "About",
  data() {
    return {
      content: null,
    }
  },
  methods: {
    async fetch() {
      const response = await fetch('https://shahmarasy.iran.liara.run/about_me');
      const data = await response.json();
      this.content = data.content
    }
  },
  beforeMount() {
    this.fetch()
  }
}
</script>
