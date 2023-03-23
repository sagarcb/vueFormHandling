<script setup>
import {watch} from "vue";

let formValues = {
  name: '',
  profileSummary: '',
  country: '',
  jobLocation: [],
  remoteWork: 'no',
  skillSet: [],
  yearsOfExperience: '',
  age: null
}

const consoleName = () => {
  console.log(formValues);
}

watch(formValues, () => {
  console.log(formValues)
})

const submitForm = () => {
  console.log('Form values', formValues);
}
</script>

<template>
  <form action="" @submit.prevent="submitForm">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name" @keyup="consoleName">
    </div>
    <div>
      <label for="name">Age</label>
      <input type="number" id="age" v-model.number="formValues.age" @keyup="consoleName">
    </div>
    <div>
      <label for="profile">Profile Summary</label>
      <textarea name="" id="profile" cols="30" rows="10" v-model="formValues.profileSummary"></textarea>
    </div>
    <div>
      <label for="country">Country</label>
      <select name="country" id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="Bangladesh">Bangladesh</option>
        <option value="India">India</option>
        <option value="USA">USA</option>
      </select>
    </div>
    <div>
      <label for="job-location">Job Location</label>
      <select name="country" multiple id="job-location" v-model="formValues.jobLocation">
        <option value="Bangladesh">Bangladesh</option>
        <option value="India">India</option>
        <option value="USA">USA</option>
      </select>
    </div>
    <div>
      <br>
      <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
      <label for="remoteWork">Open to remote work?</label>
    </div>
    <div>
      <br>
      <label>Skill Set</label>
      <input type="checkbox" id="html" value="html" v-model="formValues.skillSet">
      <label for="html">HTML</label>
      <input type="checkbox" id="css" value="css" v-model="formValues.skillSet">
      <label for="css">CSS</label>
      <input type="checkbox" id="javascript" value="Javascript" v-model="formValues.skillSet">
      <label for="javascript">Javascript</label>
    </div>
    <div>
      <br>
      <label>Years of Experience</label>
      <input
          type="radio"
          id="0-2"
          value="0-2"
          v-model="formValues.yearsOfExperience"
      >
      <label for="0-2">0-2</label>
      <input
          type="radio"
          id="3-5"
          value="3-5"
          v-model="formValues.yearsOfExperience"
      >
      <label for="3-5">3-5</label>
      <input
          type="radio"
          id="6-10"
          value="6-10"
          v-model="formValues.yearsOfExperience"
      >
      <label for="0-2">6-10</label>
    </div>
<!--    <div>-->
<!--      <button>Submit</button>-->
<!--    </div>-->
    <div>
    </div>
  </form>
</template>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /*text-align: center;*/
  color: #2c3e50;
  margin-top: 60px;
}

label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}

input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.428747;
  color: #555;
  background-color: #ffffff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
