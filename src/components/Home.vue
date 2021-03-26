<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col-lg-4">
          <div class="box">
            <Information class="mt-4"/>
          </div>
          <div class="calendar">
            <Calendar class="mt-4"/>
          </div>
        </div>
        <div class="col-lg-8 border-left">
          <h1 class="mt-4 mb-3" style="color:#525C77">Task For Today</h1>
          <div class="row">
            <div class="col-lg-3 col-md-3 col-sm-3 col-xs-3 pl-3">
              <button class="btn btn-block border rounded-pill bg-blue text-white"  @click="$bvModal.show('modal')">+ Create New</button>
            </div>
            <div class="col-lg-9 col-md-9 col-sm-9 col-xs-9 pl-1 text-center">
              <button
              class="btn btn-block border rounded-pill text-blue border-blue"
              @click="clickAction">
              Search
              <span>
              <b-icon class="search" icon="search"/></span>
              </button>
            </div>
          </div>
          <div class="tasks mt-3">
            <Card :tasks='tasks' />
          </div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <b-modal id="modal" centered title="New Task" hide-footer hideHeaderClose>
      <div class="d-block">
        <div class="form-group">
          <label for="Title"><h4>Title</h4></label>
          <input type="text" class="form-control" placeholder="Fill title">
        </div>
        <div class="form-group">
          <label for="Title"><h4>Description</h4></label>
          <textarea class="form-control" rows="3" placeholder="Fill description"></textarea>
        </div>
        <div class="form-group">
          <label for="Title"><h4>Choose Date</h4></label>
          <Calendar/>
        </div>
      </div>
      <div class="d-flex justify-content-center">
        <b-button class="mt-3 btn text-blue bg-transparent border-0" @click="$bvModal.hide('modal')">Cancel</b-button>
        <b-button class="mt-3 ml-4 btn bg-blue" @click="$bvModal.hide('modal');clickAction()">Create Task</b-button>
      </div>
    </b-modal>
  </div>
</template>

<script>
import Card from './Card'
import Information from './Information'
import Calendar from './Calendar'

export default {
  components: {
    Card,
    Information,
    Calendar
  },
  data () {
    return {
      tasks: [
        {
          id: 1,
          title: 'Daily Stand Up',
          todo: ['Dont forget prepare your report and any blocker in Front end.', 'Telling Project Manager for new assignment.'],
          status: [true]
        },
        {
          id: 2,
          title: 'Meeting With Client A',
          todo: ['Lorem Ipsum Dolor Amet', 'Lorem Ipsum Dolor Amet'],
          status: [false]
        },
        {
          id: 3,
          title: 'Meeting With Client B',
          todo: ['Lorem Ipsum Dolor Amet', 'Lorem Ipsum Dolor Amet'],
          status: [false]
        }
      ]
    }
  },
  methods: {
    clickAction () {
      alert('This feature will be added')
    }
  }
}
</script>

<style scoped>
  .bg-blue{
    background-color: #0442D0 !important;
  }
  .text-blue{
    color: #0442D0 !important;
  }
  .border-blue{
    border: 1px #0442D0 solid !important;
  }
  .search{
    position: absolute;
    right: 5%;
  }
  @media (max-width: 992px){
    .col-lg-8{
      border: none !important;
    }
  }
</style>
