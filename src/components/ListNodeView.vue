<template>
    <div>
        <div id="list-item" v-for="(item,index) in list" :key="index">
            <div id="item-name">
                <span>{{ item.name }}-></span>
            </div>
            <div id="children-item" v-if="item.children">
                <List :list="item.children"></List>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name: "List",
    props: {
        list: Array
    }
}
</script>