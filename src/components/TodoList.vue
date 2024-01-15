<template>
    <div>
        <input type="checkbox" @change="handleCheckboxChange" />
        <!-- <span>{{ todo.text }}</span> -->
    </div>
</template>

<script>

export default{
    props: ['todo'],
    methods:{
        handleCheckboxChange() {
            this.$emit('toggle, this.todo.id');
        },
    },
};



</script>