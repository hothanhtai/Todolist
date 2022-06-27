<template>
  <nav class="filter-nav">
    <button @click="updateFilter('all')" :class="{ active : current === 'all'}">View All</button>
    <button @click="updateFilter('completed')" :class="{ active : current === 'completed'}">Completed</button>
    <button @click="updateFilter('ongoing')" :class="{ active : current === 'ongoing'}">Do Not</button>
  </nav>
</template>

<script>
export default {
    props:['current'],
    methods:{
        updateFilter(by){
            this.$emit('filterChange', by)

        }
    }
}
</script>

<style>
    .filter-nav button{
        background: rgba(218, 9, 106, 0.827);
        border: none;
        color: rgb(255, 237, 237);
        outline: none;
        padding: 6px;
        border-radius: 5px;
        font-size: 12px;
        text-transform: uppercase;
        margin-right: 10px;
        letter-spacing: 1px;
        font-weight: bold;
        cursor: pointer;
    }
    .filter-nav button.active{
        color: rgb(12, 11, 11);
        background: rgb(16, 194, 161);
    }
</style>