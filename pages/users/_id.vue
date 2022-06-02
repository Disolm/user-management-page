<template>
  <div class="id-user d-flex flex-column w-50 p-3">
    <div class="id-user__title d-flex flex-column">
      <div class="id-user__name id-user_indent bg-info">
        <div class="id-user__name_header">
            Users
        </div>
        <div class="id-user__name_cell">{{ user.login }}</div>
        <div class="id-user__name_cell"> {{ user.first_name }} {{ user.family_name }} {{ user.middle_name }} </div>
      </div>
      <div class="id-user__address id-user_indent bg-info">
        <p>{{ user.address.street }}</p>
        <p>{{ user.address.suite }}</p>
        <p>{{ user.address.city }}</p>
        <p>{{ user.address.zipcode }}</p>
      </div>
      <div class="id-user__contacts id-user_indent bg-info">
        <p>{{ user.email }}</p>
        <p>{{ user.phone }}</p>
      </div>
      <div class="id-user__at id-user_indent bg-info">
        <p>{{ user.created_at }}</p>
        <p>{{ user.updated_at }}</p>
      </div>
    </div>
    <div class="id-user__buttons id-user_indent bg-light">
      <nuxt-link class="link-light" to="/">
        <button type="button" class="btn btn-primary">
          Home
        </button>
      </nuxt-link>

      <nuxt-link class="link-light" to="/">
        <button disabled type="button" class="btn btn-secondary">
          Edit
        </button>
      </nuxt-link>
    </div>

  </div>
</template>

<script>
export default {
  validate({params}) {
    return /^\d+$/.test(params.id);
  },
  async asyncData({$axios, params}) {
    const users = await $axios.$get('/json/userList.json');
    const user = users[params.id]
    return {user};
  },
  methods: {

  },

};
</script>

<style lang="scss">
.id-user {
  &__title {
    margin: 10px;
  }
  padding-top: 1em;
  margin: 0 auto;
  color: #fff;
  &__name {
    margin-bottom: 20px;
    &_header {
      font-size: 1.5em;
      margin-bottom: 10px;
    }
    &_cell {
      border-bottom: 1px solid black;
    }
  }
  &_indent {
    padding: 10px;
  }
}
</style>
