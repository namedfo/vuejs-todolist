<template>
    <form @submit.prevent>
        <h4>Create post</h4>
        <my-input
            v-focus
            v-model="post.title"
            type="text"
            placeholder="Title"
        />
        <my-input 
            v-model="post.body"
            type="text"
            placeholder="Description"
        />
        <my-button
            style="align-self: flex-end; margin-top: 15px;"
            @click="createPost"
        >
            Create
        </my-button>
    </form>
</template>

<script>
export default {
    data() {
        return {
            post: {
                id: '',
                title: '',
                body: ''
            }
        }
    },
    methods: {
        createPost() {
            this.$emit('create', this.post)
            this.post = {
                id: id = Date.now(),
                title: '',
                body: ''
            }
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
        flex-direction: column;
    }
</style>