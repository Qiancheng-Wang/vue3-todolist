<template>
    <div class="filters">
        <span class="filters active">All</span>
        <span class="filters">Done</span>
        <span class="filters">Todo</span>
    </div>
</template>

<script>
export default {
    name: "TodoFilter"
}
</script>

<style>

.filters {
  display: flex;
  margin: 24px 2px;
  color: #c0c2ce;
  font-size: 14px;
}

.filters .filters {
  margin-right: 14px;
  transition: 0.8s;
}

.filters .filters.active {
  color: #6b729c;
  transform: scale(1.2);
}

</style>