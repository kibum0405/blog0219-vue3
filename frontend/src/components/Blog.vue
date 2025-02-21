<template>
    <div>
        <String label="이름" v-model="value.name" :editMode="editMode"/>
        <String label="방문자이름" v-model="value.visitName" :editMode="editMode"/>
        <PostId offline label="게시물 ID" v-model="value.postId" :editMode="editMode" @change="change"/>
        <StringDetailGrid label="방문자이름" offline v-model="value.visitName" :editMode="editMode" @change="change"/>

        <v-divider class="border-opacity-100 my-divider"></v-divider>
        <v-layout row justify-end>
            <v-btn
                width="64px"
                color="primary"
                @click="save"
            >
                저장
            </v-btn>
        </v-layout>
    </div>
</template>


<script>

import BaseEntity from './base-ui/BaseEntity.vue'

export default {
    name: 'Blog',
    mixins:[BaseEntity],
    components:{
    },
    
    data: () => ({
        path: "blogs"
    }),
    created(){
    },
    computed:{
    },
    methods: {
    },
}
</script>
