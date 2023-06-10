<template>
    <div class="profile-info">
        <div class="profile-image">
          <img :src="user.photo" alt="profile-image"/>
        </div>
        <div class="main-info">
          <h3>{{ user.name }}</h3>
          <p>Front End Developer</p>
          <p>jameelmatar1@gmail.com</p>
        </div>
        <div class="numbers">
          <div>
            <h2>{{user.followers}}</h2>
            <p>followers</p>
          </div>
          <div>
            <h2>{{user.follow}}</h2>
            <p>following</p>
          </div>
          <div>
            <h2>{{user.likes}}</h2>
            <p>likes</p>
          </div>
        </div>
        <hr/>
        <p class="last">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>
    </div>
</template>
<script setup>
const { user } = defineProps({
    user: {
      required: true,
      type: Object,
    },
})
</script>
<style scoped>
.container{
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 5%;
}
.profile-info{
  width: 30%;
  margin-top: -9%;
}
.profile-info .profile-image{
  display: flex;
  justify-content: center;
}
.profile-info .profile-image img{
  width: 150px;
  height: 150px;
  border: 4px solid #ddd;
  border-radius: 50%;
}
.profile-info .main-info{
  text-align: center;
}
.profile-info .main-info p{
  color: #BFBDBF;
  margin: 10px 0;
}
.profile-info .numbers{
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  margin-top: 30px;
}
.profile-info .numbers h2{
  margin: 10px 0;
}
.profile-info .numbers p{
  color: #BFBDBF;
}
.profile-info hr{
  margin: 15px 0;
}
.profile-info .last{
  margin: 0 10px;
}
@media screen and (max-width:991px) {
  .profile-info{
    width: 100%;
    margin-top: -75px;
    margin-bottom: 20px;
  }
}
</style>