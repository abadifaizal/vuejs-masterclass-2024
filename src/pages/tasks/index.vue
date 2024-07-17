<script setup lang="ts">
import { supabase } from '@/lib/supabaseClient'
import { ref } from 'vue'
import { type Tables } from '../../../database/types'

const tasks = ref<Tables<'tasks'>[] | null>(null)

// we can't call await function on the top level component
// we will use self invoking function to call the function
;(async () => {
  const { data, error } = await supabase.from('tasks').select()

  if (error) {
    console.error(error)
    return
  }

  tasks.value = data
})()
</script>

<template>
  <div>
    <h1>Projects Page</h1>
    <RouterLink to="/">Go to Home</RouterLink>
    <ul>
      <li v-for="task in tasks" :key="task.id">
        {{ task.name }}
      </li>
    </ul>
  </div>
</template>
