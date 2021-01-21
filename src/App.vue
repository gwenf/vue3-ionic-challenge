<template>
  <ion-grid>
    <ion-row>
      <ion-col offset="1" size="10">
        <div class="main-content">
          <ion-grid>
            <ion-row>
              <ion-col class="ion-justify-content-between">
                <div>
                  <h1>Social Media Dashboard</h1>
                  <h4>Total Followers: 23,004</h4>
                </div>
                <div>
                  Dark Mode
                  <ion-toggle
                    @ionChange="toggleDarkMode"
                    :checked="darkMode">
                  </ion-toggle>
                </div>
              </ion-col>
            </ion-row>
          </ion-grid>

          <div class="card-container">
            <ion-grid>
              <ion-row>
                <ion-col v-for="item in items" :key="item.type">
                  <ion-card>
                    <ion-card-content class="ion-text-center">
                      <h4 class="text-username">{{ item.username }}</h4>
                      <h1 class="text-num-followers">{{ item.followers }}</h1>
                      <h4 class="text-followers">FOLLOWERS</h4>
                      <p class="text-new-followers">{{ item.newFollowers }} Today</p>
                    </ion-card-content>
                  </ion-card>
                </ion-col>
              </ion-row>
            </ion-grid>

          </div>
        </div>

        <div class="overview-content">
          <h2>Overview - Today</h2>
        </div>
      </ion-col>
    </ion-row>
  </ion-grid>
</template>

<script>
export default {
  data () {
    return {
      darkMode: false,
      items: [
        {
          type: 'facebook',
          username: '@faradayacademy',
          followers: 1987,
          newFollowers: 12
        },
        {
          type: 'twitter',
          username: '@faradayacademy',
          followers: 2837,
          newFollowers: 9
        },
        {
          type: 'instagram',
          username: '@faradayacademy',
          followers: 1987,
          newFollowers: 24
        },
        {
          type: 'YouTube',
          username: 'Faraday Academy',
          followers: 15000,
          newFollowers: 100
        }
      ]
    }
  },
  methods: {
    toggleDarkMode () {
      this.darkMode = !this.darkMode
    }
  }
}
</script>

<style scoped>
.text-num-followers {
  font-size: 50px;
  font-weight: 900px;
}
.text-new-followers {
  font-weight: 700;
  margin-top: 20px;
}
.text-followers {

}
.text-username {
  margin-bottom: 15px;
  font-size: 10px;
}
@media (prefers-color-scheme: dark) {
  :root {
    /* dark mode variables go here */
  }
}
</style>
