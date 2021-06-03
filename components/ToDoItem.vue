<template>
  <b-row class="px-3 align-items-center todo-item rounded">
    <b-col cols="auto" class="m-1 p-0 d-flex align-items-center">
      <div class="m-0 p-0 check-size">
        <font-awesome-icon
          :icon="['fas', 'square']"
          class="text-primary btn m-0 p-0 d-none"
          title="Mark as complete"
        />

        <font-awesome-icon
          :icon="['fas', 'check-square']"
          class="text-primary btn m-0 p-0"
          title="Mark as todo"
        />
      </div>
    </b-col>

    <b-col class="px-1 m-1 d-flex align-items-center">
      <input
        type="text"
        class="form-control form-control-lg border-0 edit-todo-input bg-transparent rounded px-3"
        readonly
        value="Buy groceries for next week"
        title="Buy groceries for next week"
      />
      <input
        type="text"
        class="form-control form-control-lg border-0 edit-todo-input rounded px-3 d-none"
        value="Buy groceries for next week"
      />
    </b-col>
    <div class="col-auto m-1 p-0 px-3 d-none"></div>
    <b-col cols="auto" class="m-1 p-0 todo-actions">
      <b-row class="d-flex align-items-center justify-content-end">
        <h5 class="m-0 p-0 px-2">
          <font-awesome-icon
            :icon="['fas', 'pencil-alt']"
            class="text-info btn m-0 p-0"
            title="Edit todo"
          />
        </h5>
        <h5 class="m-0 p-0 px-2">
          <font-awesome-icon
            :icon="['fas', 'trash']"
            class="text-danger btn m-0 p-0"
            title="Delete todo"
          />
        </h5>
      </b-row>
      <b-row class="todo-created-info">
        <b-col cols="auto" class="d-flex align-items-center pr-2">
          <font-awesome-icon
            :icon="['fas', 'info-circle']"
            class="my-2 text-black-50"
            title=""
          />
          <label class="date-label my-2 text-black-50">28th Jun 2020</label>
        </b-col>
      </b-row>
    </b-col>
  </b-row>
</template>
<style lang="scss" scoped>
.check-size {
  font-size: 2rem;
}
</style>
