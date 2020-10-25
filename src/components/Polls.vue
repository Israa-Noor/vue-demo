<template>
  <div>

    <h1>{{ title }}</h1>


    <ul>
      <li v-for="poll in polls" :key="poll.id">
        {{ poll.question_text  }}
      </li>
    </ul>
    <h1>{{error_message}}</h1>

    <div class="polls">
      <h1 class="question">This is my questions</h1>
      <p class="answers">lorem ipsom dolor sit  </p>

    </div>

  </div>
</template>

<script>
/*eslint-disable*/
import axios from 'axios'
export default {
  name: "Polls",
  props: {
    title: String
  },
  data() {
    return {
      polls:null,
      error_message:''
    }
  },
  created() {
    // fetch data from api or data source
    console.log('fetching data .. ')
    let configs ={
      responseType: 'json',
    }
    axios.get('http://127.0.0.1:8000/polls/question/', configs)
        .then(response =>{
      //save response data
          console.log('response has arrived')
          let data_from_server = response.data
          let status_code = response.status
          console.log(data_from_server)
          console.log(status_code)
          this.polls = data_from_server
    }).catch(error =>{
      //print error
      console.log('some error happened')
      this.error_message ="please see areeb for help"
    })
    console.log('Done fetching.')
  },
  destroyed() {},
  mounted(){}
}
</script>

<style lang="scss">
$theme-color: blue;
.polls{
  .question{
    color: blue;
  }
  .answers{
    color: #ff0000;
  }
}
</style>