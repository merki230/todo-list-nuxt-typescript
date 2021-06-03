<template>
  <b-container class="m-5 p-2 rounded mx-auto bg-light shadow">
    <b-row>
      <b-col>
        <div
          class="p-1 h1 text-primary text-center mx-auto display-inline-block"
        >
          <font-awesome-icon
            :icon="['fas', 'check']"
            class="bg-primary text-white rounded p-2"
          />
          <u>My Todo-s</u>
        </div>
      </b-col>
    </b-row>
    <b-row class="m-1 p-3">
      <b-col cols="11" class="mx-auto">
        <b-row
          class="bg-white rounded shadow-sm p-2 add-todo-wrapper align-items-center justify-content-center"
        >
          <b-col>
            <b-form-input
              class="border-0 add-todo-input bg-transparent rounded"
              type="text"
              size="lg"
              placeholder="Add new .."
            />
          </b-col>
          <b-col cols="12">
            <b-form-input
              class="border-0 add-todo-input bg-transparent rounded"
              type="date"
              size="lg"
            />
          </b-col>
          <b-col>
            <b-button variant="primary" size="sm">Add</b-button>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
    <div class="p-2 mx-4 border-black-25 border-bottom"></div>
    <b-row align-h="end" class="m-1 p-3 px-5">
      <b-col cols="auto" class="d-flex align-items-center">
        <label class="text-secondary my-2 pr-2 view-opt-label">Filter</label>
        <b-form-select
          value-field="id"
          text-field="name"
          :options="filters"
          class="custom-select custom-select-sm btn my-2"
        />
      </b-col>
      <b-col cols="auto" class="d-flex align-items-center px-1 pr-3">
        <label class="text-secondary my-2 pr-2 view-opt-label">Sort</label>
        <b-form-select
          value-field="id"
          text-field="name"
          :options="filterByDate"
          class="custom-select custom-select-sm btn my-2"
        />
        <font-awesome-icon
            :icon="['fas', 'sort-amount-up']"
            class="text-info"
            title="Ascending"
          />
          <font-awesome-icon
            :icon="['fas', 'sort-amount-down']"
            class="text-info d-none"
            title="Descending"
          />
      </b-col>
    </b-row>
    <b-row class="mx-1 px-5 pb-3 w-80">
       <b-col class="mx-auto">
         <to-do-item v-for="(item, index) in 20" :key="index"/>
       </b-col>
    </b-row>
  </b-container>
</template>

<script lang="ts">
import Vue from 'vue'
import ToDoItem from '~/components/ToDoItem.vue'

export default Vue.extend({
  components: { ToDoItem },
  data: () => ({
    filters: [
      { id: 1, name: 'All' },
      { id: 2, name: 'Completed' },
      { id: 3, name: 'Active' },
      { id: 4, name: 'Has due date' },
    ],
    filterByDate: [
      { id: 1, name: 'Added date' },
      { id: 2, name: 'Due date' },
    ],
  }),
})
</script>
