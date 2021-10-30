<template>
  <div class="user-container">
    <div class="user-details">
      <img class="user-details-avatar" :src="avatar" :alt="name" />
      <div class="user-details-info">
        <p class="user-details-paragraph">{{ name }}</p>
        <p>
          <a class="user-details-paragraph" :href="githubLink">@{{ login }}</a>
        </p>
        <p class="user-details-paragraph">Joined {{ formatedCreatedAt }}</p>
      </div>
    </div>

    <div class="user-profile">
      <p class="user-profile-bio">
        {{ bio ? bio : "This profile has no bio" }}
      </p>
      <div class="user-profile-stats">
        <div class="user-profile-box">
          <p>Repos</p>
          <p>{{ repos }}</p>
        </div>
        <div class="user-profile-box">
          <p>Followers</p>
          <p>{{ followers }}</p>
        </div>
        <div class="user-profile-box">
          <p>Following</p>
          <p>{{ following }}</p>
        </div>
      </div>

      <!-- details -->

      <div class="user-profile-details">
        <div class="user-profile-label">
          <location-icon />
          <p>
            {{ checkSocial(location) }}
          </p>
        </div>
        <div class="user-profile-label">
          <website-icon />
          <a> {{ checkSocial(blogUrl) }}</a>
        </div>
        <div class="user-profile-label">
          <twitter-icon />
          <a target="_blank">{{ checkSocial(twitterUsername) }} </a>
        </div>
        <div class="user-profile-label">
          <company-icon />
          <p>
            {{ checkSocial(company) }}
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
import moment from "moment";

export default {
  name: "user",
  props: ["user"],
  components: { LocationIcon, WebsiteIcon, TwitterIcon, CompanyIcon },
  watch: {
    user: function (value) {
      this.avatar = value.avatar_url;
      this.name = value.name;
      this.login = value.login;
      this.bio = value.bio;
      this.createdAt = value.created_at;
      this.repos = value.public_repos;
      this.followers = value.followers;
      this.following = value.following;
      this.location = value.location;
      this.blogUrl = value.blog;
      this.twitterUsername = value.twitter_username;
      this.company = value.company;
    },
  },
  data() {
    return {
      avatar: this.user.avatar_url,
      name: this.user.name,
      login: this.user.login,
      bio: this.user.bio,
      createdAt: this.user.created_at,
      repos: this.user.public_repos,
      followers: this.user.followers,
      following: this.user.following,
      location: this.user.location,
      blogUrl: this.user.blog,
      twitterUsername: this.user.twitter_username,
      company: this.user.company,
    };
  },
  methods: {
    checkSocial(value) {
      return value ? value : "Not Available";
    },
  },
  computed: {
    githubLink() {
      return `https://github.com/${this.login}`;
    },
    formatedCreatedAt() {
      return moment(this.createdAt).format("DD MMM YYYY");
    },
  },
};
</script>

<style scoped>
.user {
  padding: 4rem;
  position: relative;
}

.user-container {
  border-radius: 1.8rem;
  background-color: #f6faff;
  padding: 4rem;
  box-shadow: 1px 1px 10px 1px #4b6a9b78;
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
  background-color: #4b6a9b3f;
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
  grid-template-columns: repeat(2, 1fr);
  grid-gap: 1rem;
}

.user-profile-label {
  display: flex;
  align-items: center;
  margin: 0 auto;
}

.user-profile-label > p,
a {
  color: #4b6a9b;
  text-decoration: none;
}
</style>
