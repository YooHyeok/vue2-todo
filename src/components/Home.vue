<template>
  <v-container>
   <v-layout row wrap><!-- row wrap : vuetify의 그리드 시스템 활용 -->
    <v-flex xs6 pa-2>
      <List
        :todoList="todoList"
      />
    </v-flex>
    <v-flex xs6 pa-2><!-- xs6 = 화면 절반차지: vuetify의 그리드 시스템은 flex-box기반 가로 기준 12개로 나누어 구성됨.-->
      <!-- @listAdd : $emit의 Listener 역할 -->
      <ListAdd
        @listAdd="listAdd" 
      />
    </v-flex>
   </v-layout>
  </v-container>
</template>

<script>
import List from './List'
import ListAdd from './ListAdd.vue'

export default {
  components: {
    List,
    ListAdd
  },
  data() {
    return {
      todoList: []
    }
  },
  methods: {
    listAdd(memo) {
      this.todoList.push({
        memo, 
        status: 'created'
      })
    }
  },
}
</script>
