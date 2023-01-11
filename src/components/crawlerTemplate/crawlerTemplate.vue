<template>
    <TemplateHeader :templateHeaderData="{uris:['http://www.baidu.com','http://www.bing.com']}"/>
</template>
<script>
import TemplateHeader from '@/components/crawlerTemplate/templateHeader.vue'
export default {
    name: 'CrawlerTemplate',
    components: {
        TemplateHeader
    },
    data(){
        return {objectOfAttrs:{}};
    }
}
</script>