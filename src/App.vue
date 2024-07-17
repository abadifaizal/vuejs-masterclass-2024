<script setup lang="ts">
import Input from '@/components/ui/input/Input.vue'
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuSeparator,
  DropdownMenuTrigger
} from '@/components/ui/dropdown-menu/'
import { Avatar, AvatarFallback, AvatarImage } from '@/components/ui/avatar/'
</script>

<template>
  <nav class="flex items-center justify-between h-16 px-6 border-b bg-muted/40">
    <form class="relative w-full max-w-96 h-fit">
      <iconify-icon
        class="absolute top-[50%] left-2.5 translate-y-[-50%] text-muted-foreground"
        icon="lucide:search"
      />
      <Input type="text" placeholder="Search..." class="w-full pl-8 bg-background" />
    </form>
    <DropdownMenu>
      <DropdownMenuTrigger>
        <Avatar>
          <AvatarImage src="https://github.com/radix-vue.png" alt="@radix-vue" />
          <AvatarFallback>CN</AvatarFallback>
        </Avatar>
      </DropdownMenuTrigger>
      <DropdownMenuContent>
        <DropdownMenuLabel>My Account</DropdownMenuLabel>
        <DropdownMenuSeparator />
        <DropdownMenuItem>Profile</DropdownMenuItem>
        <DropdownMenuItem>Billing</DropdownMenuItem>
        <DropdownMenuItem>Team</DropdownMenuItem>
        <DropdownMenuItem>Subscription</DropdownMenuItem>
      </DropdownMenuContent>
    </DropdownMenu>
  </nav>
  <RouterView />
</template>
