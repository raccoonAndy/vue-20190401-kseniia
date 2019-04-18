<template>
  <div id="users">
    <h1>Список юзеров</h1>
    <div v-if="!users.length">
      Загрузка
    </div>
    <user-list v-else :list="users"></user-list>
  </div>
</template>

<script>
import UsersList from "@/components/UsersList.vue";
import axios from "axios/lib/axios";

export default {
  name: "Users",
  components: {
    "user-list": UsersList
  },
  data: () => ({
    users: []
  }),
  mounted: function() {
    this.loadUsers();
  },
  methods: {
    loadUsers: function() {
      axios
        .get("http://localhost:3004/users")
        .then(response => (this.users = response.data))
        .catch(error => console.error(error));
    }
  }
};
</script>
