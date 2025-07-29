<script setup lang="ts">
    import Autoplay from 'embla-carousel-autoplay'
    import Navbar from '@/components/Navbar.vue'
    import { Card, CardContent } from '@/components/ui/card'
    import { Carousel, CarouselContent, CarouselItem, CarouselNext, CarouselPrevious } from '@/components/ui/carousel';

    const plugin = Autoplay({
        delay: 5000,
        stopOnMouseEnter: true,
        stopOnInteraction: false
    })

    const userReviews = [
        {
            "name": "Amando G.",
            "review": "Honestly an amazing service for learning vocabulary!",
            "rating": 5
        },
        {
            "name": "Henry E.",
            "review": "The developer of the website is really nice and deserves an opportunity to showcase this.",
            "rating": 5
        },
        {
            "name": "Nikolay N.",
            "review": "This product is great because the packet's TTL never hits 0!",
            "rating": 5
        },
        {
            "name": "Ivanna B.",
            "review": "The missile knows where it is because it knows where it isn't.",
            "rating": 5
        },
    ]
</script>

<template>
    <Navbar />

    <div class="w-full h-full text-white text-center text-6xl select-none">
        <p class="pt-30">Welcome to</p>
        <p><span class="text-blue-300">Lang</span>Type!</p>
    </div>

    <div class="flex justify-center items-center pt-30 flex-col">
        <p class="text-white text-lg pb-10">See what users have said about our product:</p>
        <Carousel
            class="relative w-full max-w-xs"
            :plugins="[plugin]"
            @mouseenter="plugin.stop"
            @mouseleave="[plugin.reset(), plugin.play(), console.log('Running')];"
        >
            <CarouselContent>
                <CarouselItem v-for="review in userReviews">
                    <Card class="bg-[rgb(40,40,40)] border-0">
                        <CardContent class="flex items-center justify-center p-6">
                            <span class="text-4xl font-semibold">{{ review.name }}</span>
                        </CardContent>
                    </Card>
                </CarouselItem>
            </CarouselContent>
            
            <CarouselPrevious class="bg-[rgb(30,30,30)] border-0 text-white"/>
            <CarouselNext class="bg-[rgb(30,30,30)] border-0 text-white"/>
    </Carousel>
    </div>
</template>
