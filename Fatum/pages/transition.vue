<template>
    <div class="min-h-screen flex items-center justify-center bg-gray-900">
        <div class="text-center">
            <!-- Loading Text -->
            <h1 class="text-4xl font-semibold text-white mb-8">Loading...</h1>
            
            <!-- Analog Square Loading Animation -->
            <div class="flex space-x-2 justify-center">
                <div class="w-6 h-6 bg-gray-700 rounded square-loader square-1"></div>
                <div class="w-6 h-6 bg-gray-700 rounded square-loader square-2"></div>
                <div class="w-6 h-6 bg-gray-700 rounded square-loader square-3"></div>
                <div class="w-6 h-6 bg-gray-700 rounded square-loader square-4"></div>
                <div class="w-6 h-6 bg-gray-700 rounded square-loader square-5"></div>
                <div class="w-6 h-6 bg-gray-700 rounded square-loader square-6"></div>
                <div class="w-6 h-6 bg-gray-700 rounded square-loader square-7"></div>
                <div class="w-6 h-6 bg-gray-700 rounded square-loader square-8"></div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.square-loader {
    animation: square-appear 0.5s ease-in-out forwards;
    background-color: #374151; /* gray-700 */
}

@keyframes square-appear {
    0% {
        background-color: #374151; /* gray-700 - empty */
        transform: scale(1);
    }
    100% {
        background-color: oklch(55.4% 0.046 257.417); /* blue-500 - filled */
        transform: scale(1.1);
    }
}

/* Sequential delays for each square */
.square-1 { animation-delay: 0s; }
.square-2 { animation-delay: 0.3s; }
.square-3 { animation-delay: 0.5s; }
.square-4 { animation-delay: 0.6s; }
.square-5 { animation-delay: 1.5s; }
.square-6 { animation-delay: 2.5s; }
.square-7 { animation-delay: 2.6s; }
.square-8 { animation-delay: 2.7s; }
</style>