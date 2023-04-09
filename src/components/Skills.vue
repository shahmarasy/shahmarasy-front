<template>
  <div class="sections mobile">
    <h5 class="title">
      My Skills
    </h5>
    <hr class="in_hr">
    <div class="content">
      <table class="w-100">
        <tbody>
          <tr v-for="list in list">
            <td class="table_title">{{ list.title }}<br><span class="variables">{{ list.list }}</span><br></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <div class="sections desktop">
    <h5 class="title">
      My Skills
    </h5>
    <hr class="in_hr">
    <div class="content variables">
      <table class="w-100">
        <tbody>
          <tr v-for="list in list">
            <td class="table_title w-50">{{ list.title }}</td>
            <td>{{ list.list }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "Skills",
  data() {
    return {
      list: null,
    }
  },
  methods: {
    async fetch() {
      const response = await fetch('https://shahmarasy.iran.liara.run/skills');
      const data = await response.json();
      this.list = data
    }
  },
  beforeMount() {
    this.fetch()
  }
}
</script>
