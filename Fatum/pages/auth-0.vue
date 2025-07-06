<template>
    <div class="min-h-screen flex flex-col items-center justify-center">
        <h1 class="text-4xl">
            Current Authority Level: {{$route.name.split('').pop()}}
        </h1>
        <p class="text-lg mt-4">You are logged in as a guest with limited access.</p>
        <p class="text-lg mt-2">Please navigate to the main page for more features.</p>
        <div class="grid grid-cols-3 gap-4">
            <div class="rounded-xl p-3 w-100 bg-gray-600">
                <NuxtLink to="file">File</NuxtLink>
            </div>
            <div class="rounded-xl p-3 w-100 bg-gray-600">
                <p>2</p>
            </div>
            <div class="rounded-xl p-3 w-100 bg-gray-600">
                <p>3</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
</style>