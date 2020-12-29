<template>
  <section>
    <h1>Users page</h1>
    <ul>
      <li v-for="user of 5" :key="user">
        User {{ user }}
      </li>
    </ul>
  </section>
</template>
