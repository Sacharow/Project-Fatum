<template>
    <div class="min-h-screen flex flex-col items-center justify-center">
        <h1 class="text-4xl">
            Current Authority Level: {{$route.name.split('').pop()}}
        </h1>
        <p class="text-lg mt-4">You are logged in as a guest with limited access.</p>
        <p class="text-lg mt-2">Please navigate to the main page for more features.</p>
    </div>
</template>