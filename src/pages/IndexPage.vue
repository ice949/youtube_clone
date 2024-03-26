<template>
  <div class="video-list">
    <div v-for="video in videos" :key="video.id" class="video-item">
      <img src="../assets/mountains.jpg" alt="Thumbnail" @click="playVideo(video.id)" class="thumbnail">
      <div class="video-info">
        <div class="user-info">
          <img :src="video.userImage" alt="User Image" class="user-image">
          <div class="user-details">
            <p class="title">{{ video.title }}</p>
            <p class="date-views">{{ video.date }} | {{ video.views }} views</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      videos: [
        {
          id: 1,
          title: 'Dummy Video 1',
          thumbnail: '',
          userImage: 'https://via.placeholder.com/50',
          date: 'March 25, 2024',
          views: 1000
        },
        {
          id: 2,
          title: 'Dummy Video 2',
          thumbnail: '../assets/quasar.jpg',
          userImage: 'https://via.placeholder.com/50',
          date: 'March 24, 2024',
          views: 1500
        },
        {
          id: 3,
          title: 'Dummy Video 3',
          thumbnail: '../assets/mountains.jpg',
          userImage: 'https://via.placeholder.com/50',
          date: 'March 23, 2024',
          views: 2000
        },
        {
          id: 4,
          title: 'Dummy Video 4',
          thumbnail: '../assets/forest.jpg',
          userImage: 'https://via.placeholder.com/50',
          date: 'March 22, 2024',
          views: 2500
        },
        {
          id: 5,
          title: 'Dummy Video 5',
          thumbnail: '../assets/sunset.jpg',
          userImage: 'https://via.placeholder.com/50',
          date: 'March 21, 2024',
          views: 3000
        },
        {
          id: 6,
          title: 'Dummy Video 6',
          thumbnail: '../assets/river.jpg',
          userImage: 'https://via.placeholder.com/50',
          date: 'March 20, 2024',
          views: 3500
        }
      ]
    }
  },
  methods: {
    // playVideo(videoId) {
    //   // Emit an event to parent component to play the selected video
    //   // You can handle this functionality as needed
    // }
  }
}
</script>

<style scoped>
.video-list {
  display: flex;
  flex-wrap: wrap;
}

.video-item {
  flex: 0 0 25%;
  padding: 10px;
  box-sizing: border-box;
}

.thumbnail {
  width: 100%;
  cursor: pointer;
}

.video-info {
  margin-top: 10px;
}

.user-info {
  display: flex;
  align-items: center;
}

.user-image {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  margin-right: 10px;
}

.user-details {
  flex: 1;
}

.title {
  font-weight: bold;
}

.date-views {
  color: #666;
  font-size: 0.8em;
}
</style>
