<template>
  <div id="testi">
    <h2 class="pagetitle">{{ pageTitle }}</h2>
    <div id="myres">
      <ul v-for="entry in comments">
        <li>{{ entry.Name }} - {{ entry.Position }}</li>
        <li>{{ entry.Comment }}</li>
      </ul>
    </div>

    <!-- entry form -->
    <el-form ref="form">
      <el-form-item>
        <el-input
          type="text"
          placeholder="Your Name"
          v-model="newName"
          :rules="[{ required: true, message: 'Name is required' }]"
          maxlength="50"
          show-word-limit
        >
        </el-input>
      </el-form-item>
      <el-form-item>
        <el-input
          type="text"
          placeholder="Your Job Title"
          v-model="newJobTitle"
          :rules="[
            {
              required: true,
              message: 'Please select Activity zone',
              trigger: 'change'
            }
          ]"
          maxlength="50"
          show-word-limit
        >
        </el-input>
      </el-form-item>
      <el-form-item>
        <el-input
          :rules="[
            {
              required: true,
              message: 'Please select Activity zone',
              trigger: 'change'
            }
          ]"
          type="textarea"
          placeholder="Your Comment"
          v-model="newComment"
        ></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="submit" @click.prevent="submit">Submit</el-button>
      </el-form-item>
    </el-form>
    {{ newName }} <br />
    {{ newJobTitle }} <br />
    {{ newComment }} <br />
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      pageTitle: "Testimonials",
      newName: "",
      newJobTitle: "",
      newComment: "",
      comments: [],
      rules: {}
    };
  },
  methods: {
    submit() {
      let combine = {
        Name: this.newName,
        Position: this.newJobTitle,
        Comment: this.newComment
      };
      axios
        .post(
          "https://gurjeet-midterm.firebaseio.com/data.json",
          JSON.stringify(combine)
        )
        .then(response => {
          console.log(response);
          console.log("Your data was saved and status = " + response.status);

          axios
            .get("https://gurjeet-midterm.firebaseio.com/data.json")
            .then(response => {
              console.log(response.data);
              if (response.data) {
                this.comments = response.data;
              }
            })
            .catch(error => {
              console.log(
                "There was an error in getting data and Error = " +
                  error.response
              );
            });
        })

        .catch(error => {
          console.log(error);
        });
      // this.$refs[form].resetFields();
    }
  },
  created() {
    axios
      .get("https://gurjeet-midterm.firebaseio.com/data.json")
      .then(response => {
        console.log(response.data);
        console.log("data is loaded gurjeet");
        if (response.data) {
          this.comments = response.data;
        }
      })
      .catch(error => {
        console.log(
          "There was an error in getting data and the Error Code is " +
            error.response
        );
      });
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}
#myres {
  margin: 0 auto;
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  margin-bottom: 10px;
}
#myres ul {
  padding: 5px;
  margin: 5px;
  text-align: left;
  width: calc(50% - 20px);
  background-color: lightgrey;
  list-style-type: none;
  font-size: 1.1rem;
  border-radius: 20px;
  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.1);
}
pageTitle {
  font-size: 3rem;
  font-weight: bold;
}
#testi {
  width: 60%;
  margin: 0 auto;
}
#myres ul li {
  padding: 10px;
}
#myres ul li:first-child {
  font-weight: bold;
  font-size: 1.2rem;
  padding: 10px;
}
form {
  border: 2px solid lightgrey;
  display: block;
  width: 100%;
  margin: 0 auto;
  padding: 10px;
  border-radius: 20px;
}
input {
  display: inline-block;
  width: 50%;
  border: 2px solid lightGrey;
  font-size: 1.1rem;
  border-radius: 20px;
  padding: 10px;
  margin-top: 5px;
  font-size: 1.1rem;
}
textarea {
  display: block;
  border: 2px solid lightgrey;
  font-size: 1.1rem;
  border-radius: 20px;
  width: 100%;
  padding: 10px;
  margin-top: 5px;
}
button {
  display: block;
  background-color: green;
  color: floralwhite;
  width: 100%;
  font-size: 1.1rem;
  border-radius: 20px;
  padding: 5px;
  margin-top: 5px;
}
</style>
