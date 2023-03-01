<template>
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" />
  <link
    href="https://fonts.googleapis.com/css2?family=Hanken+Grotesk:wght@500&family=Plus+Jakarta+Sans:wght@800&display=swap"
    rel="stylesheet"
  />
  <header>
    <div class="notifications">
      <h3>Notifications</h3>
      <p class="three">{{num}}</p>
    </div>
    <button @click="toggle">
      <h5>Mark all as read</h5>
    </button>
  </header>

  <div class="articles">
    <div class="article" :class="seen? 'active' : null">
      <img src="./assets/images/avatar-mark-webber.webp" alt="" />
      <div class="noti">
        <div class="jj">
          <h3 class="name">Mark Webber</h3>
        <p>reacted to your recent post My first tournament today!  </p>
        </div>
        <p class="date">1m ago</p>
      </div>
    </div>

    <div class="article" :class="seen? 'active' : null">
      <img src="./assets/images/avatar-angela-gray.webp" alt="" />
      <div class="noti">
        <div class="jj">
          <h3 class="name">Angela Gray</h3>
          <p>followed you</p>
        </div>
        <p class="date">5m ago</p>
      </div>
    </div>

    <div class="article" :class="seen? 'active' : null">
      <img src="./assets/images/avatar-jacob-thompson.webp" alt="" />
      <div class="noti">
        <div class="jj">
          <h3 class="name">Jacob Thompson</h3>
          <p class="cont">has joined your group Chess Club</p>
        </div>
        <p class="date">1 day ago</p>
      </div>
    </div>

    <div class="article">
      <img src="./assets/images/avatar-rizky-hasanuddin.webp" alt="" />
      <div class="noti">
        <h3 class="name">Rizky Hasanuddin</h3>
        <p>
          sent you a private message 5 days ago 
          <div class="article" :class="seen? 'active' : null">
            Hello, thanks for setting up the
            Chess Club. I've been a member for a few weeks now and I'm already
            having lots of fun and improving my game.
          </div>
        </p>
      </div>
    </div>

    <div class="article">
      <img src="./assets/images/avatar-kimberly-smith.webp" alt="" />

      <div class="noti">
        <div class="jj">
          <h3 class="name">Kimberly Smith</h3>
          <p class="cont">commented on your picture</p>
        </div>
        <p class="date">1 week ago</p>
      </div>
    </div>

    <div class="article">
      <img src="./assets/images/avatar-nathan-peterson.webp" alt="" />
      <div class="noti">
        <div class="jj">
          <h3 class="name">Nathan Peterson</h3>
          <p class="cont">
            reacted to your recent post 5 end-game strategies to increase your
            win rate
          </p>
        </div>
        <p class="date">2 weeks ago</p>
      </div>
    </div>

    <div class="article">
      <img src="./assets/images/avatar-anna-kim.webp" alt="" />
      <div class="noti">
        <div class="jj">
          <h3 class="name">Anna Kim</h3>
          <p class="cont">left the group Chess Club 2</p>
        </div>
        <p class="date">weeks ago</p>
      </div>
    </div>
  </div>
</template>


<script setup lang="ts">
const seen = ref(true)
const toggle = ()=>{
  seen.value = !seen.value
  num.value = 0
}
const num = ref(3)
</script>


<style lang="scss">
html * {
  font-family: "Hanken Grotesk", sans-serif;
  font-family: "Plus Jakarta Sans", sans-serif;
  margin: 0;
  padding: 0;
  box-sizing: border-box;

  p {
    color: hsl(219, 12%, 42%);
    font-size: small;
  }
}

header {
  display: flex;
  padding: 1rem;
  justify-content: space-between;
  align-items: center;

  .notifications {
    display: flex;
    gap: 0.25rem;
    align-items: center;

    .three {
      border-radius: 4px;
      padding: 2px 5px;
      background-color: hsl(219, 85%, 26%);
      color: hsl(0, 0%, 100%);
    }
  }

  button {
    border-style: none;
    background-color: hsl(0, 0%, 100%);
    &:hover{
      color:hsl(219, 85%, 26%);
      cursor: pointer;
    }
  }
}

.articles {
  padding: 1rem;
  display: grid;
  grid-template-columns: 1fr;
  gap: 0.5rem;

  .active{
    background-color: hsl(211, 68%, 94%);
  }
  .article {
    display: flex;
    gap: 1rem;
    grid-template-columns: 1fr 1fr;
    align-items: center;
    
    padding: 0.5rem;
    img{
      height: 4rem;
    }
    .noti {
      display: flex;
      flex-direction: column;
      gap: 1rem;
      .jj {
        align-items: center;
        display: flex;
        gap: 1rem;
      }
    }
  }
}

</style>
