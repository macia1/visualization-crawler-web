<template>
    <el-form-item v-model="templateHeaderData">
        <el-form-item label="渠道" label-width="120px">
            <el-col :span="24">
                <el-input v-model="templateHeaderData" />
            </el-col>
        </el-form-item>
        <el-form-item label="顶级域名" label-width="120px">
            <el-col :span="24">
                <el-input v-model="templateHeaderData" />
            </el-col>
        </el-form-item>
    </el-form-item>
    <el-form-item label="栏目" label-width="120px">
        <el-input v-model="templateHeaderData" />
    </el-form-item>
    <el-form-item label="URI" label-width="120px" v-model="templateHeaderData">
        <el-col :span="16">
            <el-input  v-for="item,index in templateHeaderData.uris" :key="index" :value="item"></el-input>
        </el-col>
        <el-button type="primary" @click="addURI()">Add</el-button>
    </el-form-item>

</template>
<script>
export default {
    name: 'TemplateHeader',
    props: {
        templateHeaderData: Object
    },
    methods:{
        addURI(){
            alert(JSON.stringify(this.templateHeaderData.uris));
            const temp = this.templateHeaderData.uris;
            temp.push('');
            this.$set(this.templateHeaderData,"uris",temp)
            alert(JSON.stringify(temp));
            // Vue.set(this.templateHeaderData.uris, temp);
            // alert("url add click.")
        }
    }
}

</script>