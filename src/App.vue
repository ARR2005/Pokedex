<script setup lang="ts">
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
import { Button } from "@/components/ui/button"

import axios from 'axios'
import { ref, onMounted } from 'vue'

interface Pokemon {
  name: string
  url: string
}

const pokemon = ref<Pokemon[]>([]) // strongly typed

onMounted(() => {
  axios.get('https://pokeapi.co/api/v2/pokemon')
    .then(response => {
      pokemon.value = response.data.results
    })
    .catch(error => {
      console.error(error)
    })
})

</script>

<template>
    <div class=" min-w-screen min-h-screen bg-slate-400 opacity-100">
        <section class="pt-24 pb-16 px-6" > 
            <div class="relative">
                <div class="absolute inset-0 flex item-center justify-center">
                    <div class="text-[14rem] bg-gradient-to-b from-yellow-300 to-slate-300 bg-clip-text">
                        POKEDEX
                    </div>
                </div>
            </div>

            <div clas="relative z-10 text-cente py-20">
                <h1 class="text-6xl font-black mb-60 text-red-500">
                    HELLO WORLD
                </h1>
                <div class="px-6">
                    <div class="px-6 grid grid-cols-4 grid-rows-auto">
                        <Card v-for="poke in pokemon" :key="poke.name" class="m-2">
                            <CardHeader>
                                <CardTitle>{{ poke.name }}</CardTitle>
                            </CardHeader>
                            <CardContent>
                                {{ poke.url }}
                            </CardContent>
                            <CardFooter>
                                <Button variant="ghost" size="sm" class="m-auto">Outline</Button>
                            </CardFooter>
                        </Card>
                    </div>

            </div>

            </div>
        </section>
    </div>
</template>





<style scoped>
    .container {
  display: grid; 
  grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr; 
  grid-template-rows: 1fr 1fr 1fr 1fr 1fr 1fr; 
  gap: 0px 0px; 
  grid-template-areas: 
    ". . . . . ."
    ". . . . . ."
    ". . . . . ."
    ". . . . . ."
    ". . . . . ."
    ". . . . . ."; 
}
</style>