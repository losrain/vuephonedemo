<template>
<div class="login">
  <h1>登陆</h1>
</div>  
</template>


<script>
export default {
  data() {
    return {
      ruleForm2: {
        username: "",
        userpwd: ""
      }
    };
  },
  methods: {
    register() {
      this.$router.push({name: 'register'})
    },
    submitForm() {
      var self = this;
      self.$http.get("login", self.ruleForm2)
        .then(function(res) {
          if(res.success){
            self.$router.push({name: 'acticelist'});
          };
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  }
};
</script>
<style lang="less">
  .login{
    h1{
      text-align: center;
    }
    width: 500px;
    margin: auto;
  }
</style>
