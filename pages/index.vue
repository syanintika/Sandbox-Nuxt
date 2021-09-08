<template>
  <div>
    <h1>EMIT</h1>
    <div class="row">
      <div v-for="(item,i) in getListBook" :key="i" class="col-md-4">
        <class-item :name="item.name" @follow-class="getValue" />
      </div>
    </div>

    <div class="row">
      <div v-for="(item,i) in following" :key="i" class="col-md-4">
        <class-item unfollow :name="item.name" @unfollow-class="unfollow" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    getListBook() {
      return this.listBuku.filter((item,i) => i < 3);
    }
  },
  data() {
    return {
      following: [],
      listBuku: [
        { name: "Komik" },
        { name: "Novel" },
      ],
    }
  },
  methods: {
    getValue(data) {
      this.following.push(data);
    },
    unfollow(data) {
      this.following = this.following.filter(
        (follow) => follow.name != data.name
      )
    }
  },
}
</script>
