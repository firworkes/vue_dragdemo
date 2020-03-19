<template>
    <div class="hello">
        <div class="drag-field">
            <div class="item"
                draggable="true"
                @dragstart="dragstart($event, item)"
                @dragend="dragend"
                v-for="(item, index) in items" :key="index"
            >
                {{ item.label }}
            </div>
        </div>
        <div class="drop-field"
            @drop="drop"
            @dragover.prevent
        >
            <div class="item"
                v-if="droppedItem !== ''">
                {{ droppedItem }}
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: '',
        data () {
            return {
                droppedItem: '',
                items: [
                    {
                        id: 1,
                        label: '模块一'
                    },
                    {
                        id: 2,
                        label: '模块二'
                    },
                    {
                        id: 3,
                        label: '模块三'
                    }
                ]
            }
        },

        methods: {
            drop (event) {
                this.droppedItem = event.dataTransfer.getData('item')
            },
            dragstart (event, item) {
                event.dataTransfer.setData('item', item.label)
            },
            dragend (event) {
                event.dataTransfer.clearData()
            }
        }
    }
</script>

<style scoped>
    .drag-field,
    .drop-field{
        height: 10rem;
        box-sizing: border-box;
        padding: 1rem;
        background-color: #eee;
        margin-top: 1rem;
        display: flex;
        justify-content: space-around;
        align-items: center;
    }

    .item{
        width: 30%;
        height: 3rem;
        text-align: center;
        line-height: 3rem;
        font-size: .9rem;
        background-color: royalblue;
        color: #eee;
    }
    .item:hover{
        cursor: pointer;
    }
</style>