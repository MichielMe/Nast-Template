<template>
  <div>
    <h2>Home</h2>
    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Nostrum, alias eum? Deserunt ullam obcaecati labore provident. Tempore ex porro quibusdam.</p>
    <div class="flex flex-direction-col space-x-4">
      <h2>Post Your Text</h2>
      <input v-model="userInput" type="text" placeholder="Type your text here" />
      <button @click="submitPost">Submit Post</button>
      <button @click="fetchData()">Fetch Data</button>
      <div v-for="post in data" :key="post.id">
        <p>{{ post.body }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
const data = ref(null)
const apiUrl = 'http://localhost:8000/'
const userInput = ref('')

// Fetch data from API
async function fetchData() {
  const res = await fetch(apiUrl + 'post')
  data.value = await res.json()
}

// Submit data to API
async function submitPost() {
  const postData = { body: userInput.value };

  try {
    const response = await fetch(apiUrl + 'post', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify(postData)
    });

    if (!response.ok) {
      throw new Error(`HTTP error! status: ${response.status}`);
    }

    const result = await response.json();
    console.log('Post response:', result);
    userInput.value = ''; // Clear the input field after submitting
  } catch (error) {
    console.error('Error posting data:', error);
  }
}

</script>

<style scoped>
  h2 {
    margin-bottom: 20px;
    font-size: 36px;
  }
  p {
    margin: 20px 0;
  }
</style>