<template>
    <el-form :model="form" label-width="120px">
        <el-form-item label="URI Field">
            <el-input v-model="form.name" />
        </el-form-item>
        <el-form-item label="请求方法">
            <el-select v-model="form.region" placeholder="Please select http method">
                <el-option label="GET" value="GET" />
                <el-option label="POST" value="POST" />
            </el-select>
        </el-form-item>
        <el-form-item label="请求头">
            <el-form-item v-for="(item, index) of form.httpHeader" :key="index">
                <el-col :span="11">
                    <el-input type="text" placeholder="Header Name" style="width: 100%" :value="item" />
                </el-col>
                <el-col :span="2" class="text-center">
                    <span class="text-gray-500">-</span>
                </el-col>
                <el-col :span="11">
                    <el-input type="text" placeholder="Header Value" style="width: 100%" :value="item.value" />
                </el-col>
            </el-form-item>
            <el-button type="primary" @click="addHttpHeader">Add</el-button>
            <el-button @click="resetForm(formRef)">Reset</el-button>
        </el-form-item>
        <el-form-item label="Activity time">
            <el-col :span="11">
                <el-date-picker v-model="form.date1" type="date" placeholder="Pick a date" style="width: 100%" />
            </el-col>
            <el-col :span="2" class="text-center">
                <span class="text-gray-500">-</span>
            </el-col>
            <el-col :span="11">
                <el-time-picker v-model="form.date2" placeholder="Pick a time" style="width: 100%" />
            </el-col>
        </el-form-item>
        <el-form-item label="Instant delivery">
            <el-switch v-model="form.delivery" />
        </el-form-item>
        <el-form-item label="Activity type">
            <el-checkbox-group v-model="form.type">
                <el-checkbox label="Online activities" name="type" />
                <el-checkbox label="Promotion activities" name="type" />
                <el-checkbox label="Offline activities" name="type" />
                <el-checkbox label="Simple brand exposure" name="type" />
            </el-checkbox-group>
        </el-form-item>
        <el-form-item label="Resources">
            <el-radio-group v-model="form.resource">
                <el-radio label="Sponsor" />
                <el-radio label="Venue" />
            </el-radio-group>
        </el-form-item>
        <el-form-item label="Activity form">
            <el-input v-model="form.desc" type="textarea" />
        </el-form-item>
        <el-form-item>
            <el-button type="primary" @click="onSubmit">Create</el-button>
            <el-button>Cancel</el-button>
        </el-form-item>
    </el-form>
</template>

<script setup>
import { reactive } from 'vue'

// do not use same name with ref
const form = reactive({
    name: '',
    region: 'GET',
    date1: '',
    date2: '',
    delivery: false,
    type: [],
    resource: '',
    desc: '',
    httpHeader: [
        { "user-agent": "visualization-crawler" }
    ]
})

const onSubmit = () => {
    console.log('submit!')
}
</script>
