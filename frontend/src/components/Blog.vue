<template>
    <div>
        <String label="이름" v-model="value.name" :editMode="editMode"/>
        <v-divider class="border-opacity-50 my-divider my-2"></v-divider>
        <div variant="outlined" class="my-2">
            <String label="VisitName" v-model="visitNameInput" :editMode="editMode" @keydown.enter="addVisitName"/>
            <v-card v-if="value.visitName.length > 0" variant="outlined" class="pa-4 mt-2">
                <v-card-sub-title>VisitName List</v-card-sub-title>
                <li v-for="(name, index) in value.visitName" :key="index">{{ name }}</li>
            </v-card>
            <v-row class="ma-0 pa-0 mt-2">
                <v-spacer></v-spacer>
                <v-btn @click="addVisitName">VisitName 추가</v-btn>
            </v-row>
            <StringDetailGrid label="VisitName" offline v-model="value.visitName" :editMode="editMode" @change="change"/>
        </div>
        <v-divider class="border-opacity-50 my-divider my-2"></v-divider>
        <PostId offline label="postId" v-model="value.postId" :editMode="editMode" @change="change"/>
        

        <v-divider class="border-opacity-50 my-divider my-2"></v-divider>
        <v-row class="ma-0 pa-0">
            <v-spacer></v-spacer>
            <v-btn
                width="64px"
                color="primary"
                @click="save"
            >
                저장
            </v-btn>
        </v-row>
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
        path: "blogs",
        visitNameInput: '',
        value: {
            visitName: [],
        }
    }),
    created(){
    },
    computed:{
    },
    methods: {
        addVisitNameList() {
            if (this.visitNameInput.trim() !== '') {
                this.value.visitName.push(this.visitNameInput.trim());
                this.visitNameInput = '';
            }
        },
    },
}
</script>
