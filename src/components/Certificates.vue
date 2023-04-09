<template>
  <div class="sections mobile">
    <h5 class="title">My Certificates</h5>
    <hr class="in_hr" />
    <div class="content variables">
      <table class="w-100">
        <tbody>
          <tr v-for="list in list">
            <td class="table_title w-50">
              {{ list.title }}<br /><a class="variables" target="_blank" v-bind:href="list.link">Link</a><br />
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <div class="sections desktop">
    <h5 class="title">My Certificates</h5>
    <hr class="in_hr" />
    <div class="content variables">
      <table class="w-100">
        <tbody>
          <tr v-for="list in list">
            <td class="table_title w-50">{{ list.title }}</td>
            <td>
              <a class="variables" target="_blank" v-bind:href="list.link">Link</a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "Certificates",
  data() {
    return {
      list: null,
    };
  },
  methods: {
    async fetch() {
      const response = await fetch(
        "https://shahmarasy.iran.liara.run/certificates"
      );
      const data = await response.json();
      this.list = data;
    },
  },
  beforeMount() {
    this.fetch();
  },
};
</script>
