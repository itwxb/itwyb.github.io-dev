<template>
  <div class="about">
    <v-container class="container">
      <v-layout align-center justify-center row>
        <v-card class="card">
          <h3 class="stress">LINKS</h3>
          <hr>
          <div class="Grid">
            <div :key="index" class="Grid-cell" v-for="(item, index) in items">
              <h4>{{item.name}}</h4>
              <a
                :href="item.url"
                target="_blank"
                v-on:mouseout="removeShadow($event)"
                v-on:mouseover="addShadow($event)"
              >
                <v-img
                  :src="item.avatar"
                  class="grey lighten-2"
                  lazy-src="https://raw.githubusercontent.com/guanpengchn/Figure/master/pic-loading.jpeg"
                  width="100px"
                >
                  <v-layout align-center fill-height justify-center ma-0 slot="placeholder">
                    <v-progress-circular color="grey lighten-5" indeterminate></v-progress-circular>
                  </v-layout>
                </v-img>
              </a>
            </div>
          </div>
          <h3 class="stress">MAIN PACKAGES</h3>
          <hr>
          <div :key="index" v-for="(lib, index) in libs">
            <p>
              •
              <a :href="lib.url">{{lib.name}}</a>
            </p>
          </div>
        </v-card>
      </v-layout>
    </v-container>
  </div>
</template>
<script>
import { friend } from '@/config'
export default {
  data() {
    return {
      items: friend.items,
      libs: friend.libs
    }
  },
  methods: {
    addShadow: function($event) {
      $event.currentTarget.className += ' elevation-4'
    },
    removeShadow: function($event) {
      $event.currentTarget.className = $event.currentTarget.className.replace(
        / elevation-4/g,
        ' '
      )
    }
  }
}
</script>
<style scoped>
.card {
  width: 100%;
  padding: 20px 40px 40px 40px;
}
.stress {
  color: #3692d9;
  font-weight: 500;
  margin-top: 10px;
}
a {
  height: 100px;
}
h2 {
  font-size: 36px;
  line-height: 60px;
}
h3 {
  line-height: 36px;
}
h4 {
  line-height: 36px;
  text-align: center;
}
p {
  font-size: 15px;
  margin: 0px;
  line-height: 30px;
}
.Grid {
  display: flex;
  flex-wrap: wrap;
}
.Grid-cell {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-right: 20px;
}
@media only screen and (max-width: 720px) {
  p {
    font-size: 14px;
  }
  .container {
    padding: 0px;
  }
  .card {
    width: 100%;
    padding: 10px 30px 30px 30px;
  }
  .Grid-cell {
    flex: auto;
  }
}
</style>

