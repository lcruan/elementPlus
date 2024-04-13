<script setup>

        import { ref, reactive } from 'vue'

        //默认选中的标签名称
        const selectedName = ref("2")

        //选中标签触发的回调
        const tabClick = (tab, event) => {
            console.log("tab", tab.props, "event", event)
        }

        const tab = reactive({
            arr: [
                { name: "1", title: '一起学web', content: '内容1' },
                { name: "2", title: '一起学web', content: '内容2' },
                { name: "3", title: '17xueweb.com', content: '内容3' },
            ]
        })

        //添加
        const tabAdd = () => {
            let index = tab.arr.length
            index++

            tab.arr.push({
                name: index,
                title: '新选项卡' + index,
                content: '内容' + index
            })
        }

        //移除
        const tabRemove = (name) => {
            console.log("name:", name)

            const index = tab.arr.findIndex((value) => {
                return value.name === name
            })

            tab.arr.splice(index, 1) //移除元素
        }
        
    </script>

    <template>

        <h3>标签页</h3>
        <el-tabs v-model="selectedName" @tab-click="tabClick">
            <el-tab-pane label="一起学web" name="1">内容1</el-tab-pane>
            <el-tab-pane label="一起学web" name="2">内容2</el-tab-pane>
            <el-tab-pane label="17xueweb.com" name="3">内容3</el-tab-pane>
        </el-tabs>

        <h3>卡片风格</h3>
        <el-tabs v-model="selectedName" @tab-click="tabClick" type="card">
            <el-tab-pane label="一起学web" name="a">内容1</el-tab-pane>
            <el-tab-pane label="一起学web" name="b">内容2</el-tab-pane>
            <el-tab-pane label="17xueweb.com" name="b">内容3</el-tab-pane>
        </el-tabs>

        <h3>带有边框的卡片风格</h3>
        <el-tabs v-model="selectedName" @tab-click="tabClick" type="border-card">
            <el-tab-pane label="一起学web" name="A">内容1</el-tab-pane>
            <el-tab-pane label="一起学web" name="B">内容2</el-tab-pane>
            <el-tab-pane label="17xueweb.com" name="C">内容3</el-tab-pane>
        </el-tabs>

        <h3>动态添加</h3>
        <el-button @click="tabAdd">添加</el-button>

        <el-tabs v-model="selectedName" @tab-remove="tabRemove" closable type="card">
            <el-tab-pane v-for="(value, key) in tab.arr" :key="value.name" :label="value.title" :name="value.name">
                {{ value.content }}
            </el-tab-pane>
        </el-tabs>

    </template>

    <style scoped>
    
    </style>