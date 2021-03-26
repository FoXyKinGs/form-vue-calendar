<template>
  <div>
    <div v-for="(item, i) in data" :key="i" class="card shadow rounded-lg mt-2 mb-4">
      <div class="card-body">
        <h5 class="card-title" style="color:#525C77">{{item.title}}
          <span>
            <button
            v-if="item.status[0] === false"
            @click="changeComplete(item.id)"
            style="background-color: #F2F4F8; color: #D3D5DB"
            class="btn border ml-4">
            <span>
                <b-icon icon="check"/>
              </span>
            Set as complete
            </button>
            <button v-else @click="changeComplete(item.id)" class="btn border ml-4 text-pink bg-pink">
              <span>
                <b-icon icon="check"/>
              </span>
              Complete
            </button>
          </span></h5>
        <div style="line-height: 0;" class="mb-3 mt-3">
        <p v-for="(item, i) in item.todo" :key="i" class="task card-text">{{i + 1}}. {{item}}</p>
        </div>
        <span class="option-task">
          <b-icon icon="pencil-fill" class="mr-3" style="cursor: pointer" @click="clickAction"/>
          <b-icon icon="trash-fill" style="cursor: pointer" @click="clickAction"/>
        </span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['tasks'],
  data () {
    return {
      data: this.tasks
    }
  },
  methods: {
    changeComplete (e) {
      alert(`This feature will be added, your task confirmer : ${this.data[e - 1].title}`)
    },
    clickAction () {
      alert('This feature will be added')
    }
  }
}
</script>

<style scoped>
  .text-pink{
    color: #FB3453;
  }

  .bg-pink{
    background-color: #FEEAEB;
  }

  .task{
    font-size: 13px;
    color: #525C77;
  }

  .rounded-lg{
    border-radius: 10px !important;
  }

  .option-task{
    position: absolute;
    right: 2%;
    bottom: 5%;
    color: #525C77 !important;
  }
</style>
