<template>
    <div>
        <!-- 동일하 레이아웃이 여러개 반복되기 위해 v-for 속성 사용 -->
        <!-- key는 중복될 수 있으므로 index를 사용한다. (수정/삭제시 필수) -->
        <v-card
            class="pa-3"
            v-for="(list, index) in todoList"
            :key="index"
        >
            <p>{{list.memo}}</p> <!-- 할일 내용 -->
            <v-btn fab text x-small color="green"><i class="fas fa-check">완료</i></v-btn>
            <v-btn fab text x-small color="blue"><i class="fas fa-redo-alt">부활</i></v-btn>
            <v-btn fab text x-small color="red"><i class="fas fa-trash-alt">제거</i></v-btn>
        </v-card>
    </div>
</template>
<script>

export default {
    props: ['todoList'],

}
</script>
