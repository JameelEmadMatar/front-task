<template>
    <div class="profile-content">
        <div class="interaction">
          <div class="links">
            <p>PHOTOS</p>
            <p>LIKES</p>
          </div>
          <div class="btns">
            <button>Edit profile</button>
            <button>Add friends</button>
          </div>
        </div>
        <div class="photos">
          <div class="img-div" v-for="img of user.images_list" :key="img.id">
            <img :src="img" alt="image"/>
          </div>
        </div>
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
.profile-content{
  width: 65%;
}
.profile-content .interaction{
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 20px 0;
}
.profile-content .interaction .links{
  display: flex;
  gap: 20px;
  align-items: center;
  cursor: pointer;
}
.profile-content .interaction .links p:first-child{
  font-weight: bold;
}
.profile-content .interaction .btns button{
  background-color: var(--main-color);
  color: #fff;
  border-radius: 5px;
  border: none;
  outline: none;
  padding: 10px 20px;
  margin: 0 5px;
  box-shadow: 5px 5px 5px #000000bf;
  transition: 1s;
  font-weight: bold;
  cursor: pointer;
}
.profile-content .interaction .btns button:hover{
  padding: 15px 40px;
  background-color: #fff;
  color: var(--main-color);
  border:1px solid var(--main-color)
}
.profile-content .photos{
  display: flex;
  gap: 5%;
  align-items: center;
  flex-wrap: wrap;
  margin: 25px 0;
}
.profile-content .photos .img-div{
  margin: 10px 0;
  width: 30%;
  overflow: hidden;
  box-shadow: 10px 10px 5px #4449;
  height: 150px;
  transition: 0.5s;
}
.profile-content .photos .img-div:hover{
  transform: scale(1.2);
}
.profile-content .photos .img-div img{
  width: 100%;
  max-width: 100%;
  height: 100%;
}
@media screen and (max-width:991px) {
    .profile-content{
        width: 100%;
        margin: 20px 0;
    }
}
@media screen and (max-width:575px) {
    .profile-content .interaction{
        flex-direction: column;
        align-items: start;
        gap: 10px 0;
    }
    .profile-content .interaction .btns{
        align-self: flex-end;
    }
    .profile-content .photos .img-div{
        width: 47%;
    }
}
</style>