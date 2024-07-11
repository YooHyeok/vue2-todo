<template>
    <div>
        <!-- 텍스트 필드 -->
        <v-textarea 
        outline
        v-model="memo"
        label="투두리스트를 입력해 주세요"
        value=""
        ></v-textarea>
        <!-- 추가 버튼 -->
        <v-btn @click="listAdd">리스트 추가</v-btn>
    </div>
</template>
<script>
export default {
    data() {
        return {
            memo : null
        }
    },
    methods: {
        listAdd() {
            console.log("리스트 추가")
            if (!this.memo) {
                alert('할 일을 입력해 주세요')
                return;
            }
            this.$emit("listAdd", this.memo)
        }
    }
}
</script>