<template>
  <div class="container">
      <div class="row">
      <form action="">
          <div class="row">
              <div class="col-sm-8 col-md-6 offset-sm-2 offset-md-3 form-group">
              <label for="">Enter...</label>
              <textarea class="form-group" name="" id="" cols="30" rows="10" v-model="item"></textarea>
            </div>          
          </div>
          <div class="row">
            <div class="col-sm-8 col-md-6 offset-sm-2 offset-md-3 form-group">
                <button class="btn btn-success" @click.prevent="createNew">Add</button>
            </div>
          </div>
      </form>
  </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            item: ''
        }
    },
    methods: {
        createNew() {
           if (this.item == '') {
               return false;
           } else {
                this.$emit('itemAdded', this.item);
                this.item = '';
           }
        }
    }
}
</script>

<style scoped>
   textarea {
       width: 100%;
       resize: none;
   }

   form {
       width: 100%;
   }
</style>
