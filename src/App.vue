<template>
  <main>
    <div class="container">
      <h1>Hello, welcome to the todolist</h1>
      <div class="input-add">
        <input type="text" name="todo" />
        <button>
          <i class="plus"></i>
        </button>
      </div>

      <div class="filters">
        <span class="filters active">All</span>
        <span class="filters">Done</span>
        <span class="filters">Todo</span>
      </div>

      <div class="todo-list">
        <div class="todo-item">
          <label>
            <input type="checkbox"/>
            Todo1
            <span class="check-button"></span>
          </label>
        </div>
        <div class="todo-item">
          <label>
            <input type="checkbox"/>
            Todo2
            <span class="check-button"></span>
          </label>
        </div>
        <div class="todo-item">
          <label>
            <input type="checkbox"/>
            Todo3
            <span class="check-button"></span>
          </label>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Helvetica, "PingFang SC", "Microsoft Yahei", san-serif;
}

main {
  width: 100vw;
  height: 100vh;
  display: grid;
  align-items: center;
  justify-content: center;
  background: rgb(203, 210, 240);
}

.container {
  width: 100%;
  max-width: 600px;
  box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.15);
  border-radius: 24px;
  padding: 48px 28px;
  background-color: rgb(245, 246, 252);
}

h1 {
  margin: 24px 0;
  font-size: 28px;
  color: #414873;
}

.input-add {
  position: relative;
  display: flex;
  align-items: center;
}

.input-add input {
  padding: 16px 52px 16px 18px;
  border-radius: 48px;
  border: none;
  outline: none;
  box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.08);
  width: 100%;
  font-size: 16px;
  color: #626262;
}

.input-add button {
  width: 46px;
  height: 46px;
  border-radius: 50%;
  background: linear-gradient(#c0a5f3, #7f95f7);
  border: none;
  outline: none;
  color: white;
  position: absolute;
  right: 0px;
}

.input-add .plus {
  display: block;
  width: 100%;
  height: 100%;
  background: linear-gradient(#fff, #fff), linear-gradient(#fff, #fff);
  background-size: 50% 2px, 2px 50%;
  background-position: center;
  background-repeat: no-repeat;
}

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

.todo-list {
  display: grid;
  row-gap: 14px;
}

.todo-item {
  background: white;
  padding: 16px;
  border-radius: 8px;
  color: #626262;
}

.todo-item label{
  position: relative;
  display: flex;
  align-items: center;
}

.todo-item label .check-button {
  position: absolute;
  top: 0;
}

.todo-item label .check-button::before,
.todo-item label .check-button::after
 { 
   content: "";
   display: block;
   position: absolute;
   width: 18px;
   height: 18px;
   border-radius: 50%;
}

.todo-item label .check-button::before {
  border: 1px solid #b382f9;
}

.todo-item label .check-button::after{
  transition: 0.4s;
  background: #b382f9;
  transform: translate(1px, 1px) scale(0.8);
  opacity: 0;
}

.todo-item input {
  margin-right: 16px;
  opacity: 0;
}

.todo-item input:checked + span.check-button::after {
  opacity: 1;
}
</style>
