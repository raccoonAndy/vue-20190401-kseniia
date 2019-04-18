<template id="users">
  <table class="table table-bordered">
    <thead>
      <tr>
        <th>Name</th>
        <th>E-mail</th>
        <th>Phone</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="user in list" :key="user.id">
        <td>
          <router-link :to="'/edit/' + user.index">
            {{ user.name.first }} {{ user.name.last }}
          </router-link>
        </td>
        <td>{{ user.company }}</td>
        <td>{{ user.phone }}</td>
      </tr>
    </tbody>
    <tfoot>
      <tr>
        <td colspan="3">Всего пользователе {{ total }}</td>
      </tr>
    </tfoot>
  </table>
</template>

<script>
export default {
  name: "UsersList",
  props: {
    list: {
      type: Array,
      required: true
    }
  },
  computed: {
    total: function() {
      return this.list.length;
    }
  }
};
</script>
