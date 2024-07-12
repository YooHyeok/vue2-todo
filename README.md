# $emit

1. [자식 컴포넌트] $emit 리스너 정의
    ```vue
    <template>
        <v-btn @click="emitListener">전송</v-btn>
    </template>
    <script>
    export default {
        data() {
            return {emitData: "emitData"}
        },
        methods: {
            emitListener() {
                this.$emit('onEmit', this.emitData)
            }
        }
    }
    </script>
    ```

2. [부모 컴포넌트] 정의된 emit리스너에 핸들러 등록
    ```vue
    <template>
    <EmitComponent @onEmit="emitHandler"/>
    </template>
    <script>
    export default {
        data() {
            return {emitDatas: []}
        },
        methods: {
            emitHandler(emitData) {
                emitDatas.push(emitData)
            }
        }
    }
    </script>
    ```

