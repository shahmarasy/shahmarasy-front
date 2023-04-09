<template>
  <div class="sections mobile">
    <h5 class="title">
      Contact Me
    </h5>
    <hr class="in_hr">
    <div class="content variables">
      <table class="w-100">
        <tbody>
          <tr v-for="list in list">
            <td class="table_title">{{ list.title }}<br>
              <a class="variables" v-if="list.title == 'Email'" v-bind:href="'mailto:' + list.content">{{ list.content
              }}</a>
              <a class="variables" v-if="list.title != 'Email'" v-bind:href="list.content">@shahmarasy</a>
              <br>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <div class="sections desktop">
    <h5 class="title">
      Contact Me
    </h5>
    <hr class="in_hr">
    <div class="content variables">
      <table class="w-100">
        <tbody>
          <tr v-for="list in list">
            <td class="table_title w-50">{{ list.title }}</td>
            <td>
              <a class="variables" v-if="list.title == 'Email'" v-bind:href="'mailto:' + list.content">{{ list.content
              }}</a>
              <a class="variables" v-if="list.title != 'Email'" v-bind:href="list.content">{{ list.content }}</a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
  data() {
    return {
      list: null,
    }
  },
  methods: {
    async fetch() {
      const response = await fetch('https://shahmarasy.iran.liara.run/contact');
      const data = await response.json();
      this.list = data
    }
  },
  beforeMount() {
    this.fetch()
  }
}
</script>

<style scoped></style>
