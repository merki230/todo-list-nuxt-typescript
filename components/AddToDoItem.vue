<template>
  <b-form @submit.prevent="onSubmit">
    <b-row
      align-v="center"
      align-h="center"
      class="bg-white rounded-sm add-todo-wrapper"
    >
      <b-col>
        <b-form-input
          class="border-0 add-todo-input rounded"
          type="text"
          size="lg"
          placeholder="Add new .."
          v-model="formData.label"
          required
        />
      </b-col>
      <b-col cols="12">
        <b-form-input
          class="border-0 add-todo-input rounded"
          type="date"
          size="lg"
          v-model="formData.dueDate"
          required
        />
      </b-col>
      <b-col class="d-flex justify-content-end">
        <b-button type="submit" variant="primary" size="sm">Add</b-button>
      </b-col>
    </b-row>
  </b-form>
</template>
<script lang="ts">
import Vue from 'vue'
import {Item} from '~/models/Item'
export default Vue.extend({
  data(){
    return{
        formData:{
          isCheck:false
        } as Item
    }
  },
  methods:{
    onSubmit(){
      this.formData.createDate= new Date();

      this.$emit('onSubmit', this.formData)
      this.formData = {
         isCheck:false
      } as Item
    }
  }
})
</script>
