<template id="userForm">
  <form>
    <div class="form-group row">
      <label for="inputName" class="col-sm-2 col-form-label">Name</label>
      <div class="col-sm-10">
        <input type="email" class="form-control" id="inputName" placeholder="Email">
      </div>
    </div>
    <div class="form-group row">
      <label for="inputEmail" class="col-sm-2 col-form-label">Email</label>
      <div class="col-sm-10">
        <input type="email" class="form-control" id="inputEmail" placeholder="Email">
      </div>
    </div>
    <div class="form-group row">
      <label for="inputPhone" class="col-sm-2 col-form-label">Password</label>
      <div class="col-sm-10">
        <input type="tel" class="form-control" id="inputPhone" placeholder="Phone">
      </div>
    </div>
  </form>
</template>

<script>
export default {
  name: "UsersForm",
  template: "#userForm"
};
</script>
