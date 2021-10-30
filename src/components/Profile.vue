<template>
  <div class="user-container">
    <div class="user-details">
      <img class="user-details-avatar" />
      <div class="user-details-info">
        <p class="user-details-paragraph"></p>
        <p><a class="user-details-paragraph" href="#"></a></p>
        <p class="user-details-paragraph">Joined ...</p>
      </div>
    </div>

    <div class="user-profile">
      <p class="user-profile-bio">
        {{ "This profile has no bio" }}
      </p>
      <div class="user-profile-stats">
        <div class="user-profile-box">
          <p>Repos</p>
          <p></p>
        </div>
        <div class="user-profile-box">
          <p>Followers</p>
          <p></p>
        </div>
        <div class="user-profile-box">
          <p>Following</p>
          <p></p>
        </div>
      </div>

      <!-- details -->

      <div class="user-profile-details">
        <div class="user-profile-label">
          <location-icon />
          <p>
            {{ "Not Available" }}
          </p>
        </div>
        <div class="user-profile-label">
          <website-icon />
          <a> "Not Available" }} </a>
        </div>
        <div class="user-profile-label">
          <twitter-icon />
          <a target="_blank"> </a>
        </div>
        <div class="user-profile-label">
          <company-icon />
          <p>
            {{ "Not Available" }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LocationIcon from "../icons/Location.vue";
import WebsiteIcon from "../icons/Website.vue";
import TwitterIcon from "../icons/Twitter.vue";
import CompanyIcon from "../icons/Company.vue";

export default {
  components: { LocationIcon, WebsiteIcon, TwitterIcon, CompanyIcon },
};
</script>

<style scoped>
.user {
  padding: 4rem;
  position: relative;
}

.user-container {
  border: 2px solid #b9d6fb;
  border-radius: 1.8rem;
  background-color: #f6faff;
  padding: 4rem;
}

.user-details {
  display: flex;
  align-items: center;
}

.user-details-avatar {
  width: 10rem;
  border-radius: 50%;
}

.user-details-info {
  margin-left: 2rem;
}

.user-details-paragraph {
  font-size: 1.6rem;
  font-weight: 600;
  padding: 0.6rem;
}

/* sggsgs */

.user-profile {
  margin-top: 2.5rem;
  font-size: 1.5rem;
  color: #4b6a9b;
  line-height: 2.5rem;
}

.user-profile-stats {
  display: flex;
  justify-content: space-between;
  background-color: rgb(226, 230, 248);
  margin: 1.5rem 0;
  padding: 2rem 2.5rem;
  border-radius: 1.2rem;
  font-weight: 600;
}

.user-profile-box {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.user-profile-details {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  grid-gap: 1rem;
}

.user-profile-label {
  display: flex;
  align-items: center;
}

.user-profile-label > p,
a {
  color: #4b6a9b;
  text-decoration: none;
}

@media (min-width: 500) {
  .user {
    padding: 3rem 3.5rem;
  }

  .user-info-avatar {
    width: 117px;
  }

  .user-info-headline {
    font-size: 2.6rem;
  }

  .user-profile {
    margin-top: 2.5rem;
  }

  .user-profile-stats {
    margin: 2.5rem 0;
  }

  .user-profile-stats > div {
    align-items: flex-start;
  }

  .user-profile-details {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 500) {
  .user-profile {
    margin-left: 15rem;
    margin-top: -1rem;
  }

  .user-info-avatar {
    margin-right: 1rem;
  }

  .user-info-details {
    display: flex;
    justify-content: space-between;
    width: 100%;
  }

  .user-info-joined {
    margin-top: 1rem;
  }

  .user-profile-bio {
    width: 90%;
  }
}
</style>
