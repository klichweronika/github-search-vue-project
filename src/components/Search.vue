<template>
  <div class="search-container">
    <div class="search">
      <input
        class="search - input"
        ref="username"
        type="text"
        placeholder="Search Github username..."
      />
    </div>
    <span class="error-message"></span>
    <button class="search-button">Search</button>
  </div>
</template>

<script></script>

<style scoped>
.search-container {
  background-color: #f6faff;
  padding: 1rem;
  border-radius: 1.8rem;
  margin-bottom: 2rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: relative;
}

.search {
  display: flex;
  align-items: center;
  width: 100%;
  margin-left: 0.5rem;
  background-color: transparent;
  border: none;
  font-size: 2rem;
}

.search-input {
  margin-left: 1.5rem;
  border: none;
  background: none;
  width: 60%;
}

.search:focus {
  outline: none;
}

.search-input::placeholder {
  color: #4b6a9b;
}

.error-message {
  position: absolute;
  color: #f74646;
  right: 11rem;
  font-size: 1.2rem;
  font-weight: bold;
}

.search-button {
  border: none;
  background-color: #0079ff;
  color: #fff;
  cursor: pointer;
  font-size: 1.4rem;
  font-weight: bold;
  padding: 1.7rem 2.1rem;
  border-radius: 1.4rem;
}

.search-button:hover {
  opacity: 0.7;
}

@media (min-width: 500px) {
  .search-input {
    width: 70%;
  }

  .err {
    font-size: 1.5rem;
    right: 12rem;
  }
}
</style>
