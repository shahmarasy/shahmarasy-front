<template>
  <div class="sections mobile">
    <h5 class="title">
      My Experience
    </h5>
    <hr class="in_hr">
    <div class="content ">
      <table class="w-100">
        <tbody>
          <tr v-for="list in list">
            <td class="table_title">{{ list.company }}
              <br>
              <span class="bracket">[</span><span class="variables">'{{ list.start }}-{{ list.end }}'</span><span
                class="bracket">]</span>
              <br><span class="variables">{{ list.position }}</span><br><br>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <div class="sections desktop">
    <h5 class="title">
      My Experience
    </h5>
    <hr class="in_hr">
    <div class="content variables">
      <table class="w-100">
        <tbody>
          <tr v-for="list in list">
            <td class="table_title w-50">{{ list.company }}<span class="bracket">[</span><span class="variables">'{{
              list.start }}-{{ list.end }}'</span><span class="bracket">]</span></td>
            <td>{{ list.position }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "Experience",
  data() {
    return {
      list: null,
    }
  },
  methods: {
    async fetch() {
      const response = await fetch('https://shahmarasy.iran.liara.run/experience');
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
