<script setup lang="ts">
import {
  Card,
  CardContent,
  CardDescription,
  CardFooter,
  CardHeader,
  CardTitle,
} from '@/components/ui/card'
</script>

<template>
    <div class=" min-w-screen min-h-screen bg-slate-400 opacity-20">
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
                <div class="px-50">
                    <Card>
                        <CardHeader>
                        <CardTitle>Card Title</CardTitle>
                        <CardDescription>Card Description</CardDescription>
                        </CardHeader>
                        <CardContent>
                        Card Content
                        </CardContent>
                        <CardFooter>
                        Card Footer
                        </CardFooter>
                    </Card>
                    
                </div>
            </div>
        </section>
    </div>
</template>


<style scoped>

</style>