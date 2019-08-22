<template>
  <div class="video-player">
    <div class="video-container">
      <iframe width="640" height="360" :src="this.activeVideo.youtubeURL" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
      <h3>{{this.activeVideo.title}}</h3>
      <div class="row">
        <p>{{this.activeVideo.views}} views</p> 
        <p>{{this.activeVideo.likes}} <button>Like</button></p>
      </div>
    </div>
  </div>
</template>

<script>
let videos = [
  {
    id: 1,
    title: "What a play!",
    thumbnail:
      "https://d3am56o2kzlvb7.cloudfront.net/6856711c-f0ad-4f10-8f4d-711b8183db8c/thumbnails/testvid-01_tumb.0000030.jpg",
    youtubeURL: "https://d3am56o2kzlvb7.cloudfront.net/6856711c-f0ad-4f10-8f4d-711b8183db8c/mp4/testvid-01_Mp4_Avc_Aac_16x9_1280x720p_24Hz_4.5Mbps_qvbr.mp4",
    creator: "Football League",
    likes: 0,
    views: 0
  },
  {
    id: 2,
    title: "Dope Tech: Camera Robots!",
    thumbnail:
      "https://i.ytimg.com/vi/UIwdCN4dV6w/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLDhlan32jHSvicGZezDFPjAOdXGUA",
    youtubeURL: "https://www.youtube.com/embed/UIwdCN4dV6w",
    creator: "Marques Brownlee",
    likes: 0,
    views: 0
  },
  {
    id: 3,
    title: "Let's Talk About Tesla Roadster 2020!",
    thumbnail:
      "https://i.ytimg.com/vi/ctx4YBEdOxo/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLBDnlrC2rVwXamNkicEEbc3Mf4T0w",
    youtubeURL: "https://www.youtube.com/embed/ctx4YBEdOxo",
    creator: "Marques Brownlee",
    likes: 0,
    views: 0
  },
  {
    id: 4,
    title: "Talking Tech with Neil deGrasse Tyson!",
    thumbnail:
      "https://i.ytimg.com/vi/pqQrL1K0Z5g/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLA5hTiwkz4Tr1w1hSMhPlwtmQeyYw",
    youtubeURL: "https://www.youtube.com/embed/pqQrL1K0Z5g",
    creator: "Marques Brownlee",
    likes: 0,
    views: 0
  },
  {
    id: 5,
    title: "The Apple Ecosystem: Explained!",
    thumbnail:
      "https://i.ytimg.com/vi/KB4_WIPE7vo/hqdefault.jpg?sqp=-oaymwEZCNACELwBSFXyq4qpAwsIARUAAIhCGAFwAQ==&rs=AOn4CLCCxXm7aoPShOwON74nhMlGYMUkHw",
    youtubeURL: "https://www.youtube.com/embed/KB4_WIPE7vo",
    creator: "Marques Brownlee",
    likes: 0,
    views: 0
  }
];

export default {
  name: 'VideoPlayer',
  data () {
    return {
        videos,
        activeVideo: videos[0]
    }
  },
  methods: {
    chooseVideo(video){
      //SET VIDEO AS ACTIVE VIDEO
      this.activeVideo = video;
      //INCREASE THE VIDEOS VIEWS BY 1
      video.views += 1;
    }
  }
}
</script>

<style scoped>
  .thumbnail{
    display:flex;
  }
  .thumbnail img{
    width:168px;
  }

.thumbnail-info{
    margin-left:20px;
    text-align: left;

}

.thumbnail h3{
    font-size:16px;
}

h3,
p{
    margin:0;
    padding:0;
}

.thumbnail-views{
    font-size:14px;
}
.video-player{
    display:flex;
    width:1200px;
    margin:auto;
}

.video-container{
    margin-right:40px;
}

.row{
    display:flex;
    justify-content:space-between;
}

button{
    background:#D0021B;
    color:white;
    border:none;
    padding:10px 20px;
}
</style>