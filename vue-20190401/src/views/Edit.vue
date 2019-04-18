<template>
  <div id="edit">
    <h2>Edit user {{ id }}</h2>
    <user-form></user-form>
  </div>
</template>

<script>
import UsersForm from "@/components/UsersForm.vue";
import axios from "axios/lib/axios";

export default {
  name: "Edit",
  components: {
    "user-form": UsersForm
  },
  computed: {
    id() {
      return this.$route.params.id;
    }
  },
  mounted: function() {
    this.loadUser();
  },
  methods: {
    loadUser: function() {
      axios
        .get("http://localhost:3004/users/" + this.id)
        .then(response => (this.users = response.data))
        .catch(error => console.error(error));
    }
  }
};
</script>
