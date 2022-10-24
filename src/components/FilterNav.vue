<template>
<nav class="filter-nav">
<button @click="updateFilter('all')"
:class="{ active: current === 'all'}"> View All</button>

<button @click="updateFilter('completed')" :class="{ active: current === 'completed'}"> completed</button>
<button @click="updateFilter('ongoing')" :class="{ active: current === 'ongoing'}"> ongoing</button>
</nav>  </template>

<script>
export default {
methods: {
    updateFilter(by){
        this.$emit('filterChange', by)

    }
}
}
</script>

<style>
.filter-nav button{
    background: none;
    border: none;
    color: black;
    outline: none;
    text-transform: uppercase;
    font-size: 17px;
    margin-right: 10px;
    cursor: pointer;
}
.filter-nav button.active{
 border-bottom-color: rgb(65, 29, 155);
}

</style>