<template>
    <div class="min-h-screen flex items-center justify-center bg-gray-900">
        <div class="text-center">
            <!-- Loading Text -->
            <h1 class="text-4xl font-semibold text-white mb-8">Loading...</h1>
            
            <!-- Block Loading Animation -->
            <div class="flex space-x-2 justify-center">
                <div class="w-4 h-4 bg-blue-500 rounded animate-pulse delay-0"></div>
                <div class="w-4 h-4 bg-blue-500 rounded animate-pulse delay-75"></div>
                <div class="w-4 h-4 bg-blue-500 rounded animate-pulse delay-150"></div>
                <div class="w-4 h-4 bg-blue-500 rounded animate-pulse delay-300"></div>
                <div class="w-4 h-4 bg-blue-500 rounded animate-pulse delay-500"></div>
            </div>
            
            <!-- Alternative: Bouncing Blocks -->
            <div class="flex space-x-2 justify-center mt-8">
                <div class="w-3 h-8 bg-green-500 rounded animate-bounce delay-0"></div>
                <div class="w-3 h-8 bg-green-500 rounded animate-bounce delay-100"></div>
                <div class="w-3 h-8 bg-green-500 rounded animate-bounce delay-200"></div>
                <div class="w-3 h-8 bg-green-500 rounded animate-bounce delay-300"></div>
            </div>
            
            <!-- Loading Bar -->
            <div class="w-64 h-2 bg-gray-700 rounded-full mt-8 mx-auto">
                <div class="h-full bg-blue-500 rounded-full loading-bar"></div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.loading-bar {
    width: 0%;
    animation: loading 2s ease-in-out infinite;
}

@keyframes loading {
    0% {
        width: 0%;
    }
    50% {
        width: 100%;
    }
    100% {
        width: 0%;
    }
}

/* Custom block animation */
.animate-pulse {
    animation: pulse 1.5s ease-in-out infinite;
}

@keyframes pulse {
    0%, 100% {
        opacity: 0.3;
        transform: scale(0.8);
    }
    50% {
        opacity: 1;
        transform: scale(1.2);
    }
}

.delay-0 { animation-delay: 0ms; }
.delay-75 { animation-delay: 75ms; }
.delay-100 { animation-delay: 100ms; }
.delay-150 { animation-delay: 150ms; }
.delay-200 { animation-delay: 200ms; }
.delay-300 { animation-delay: 300ms; }
.delay-500 { animation-delay: 500ms; }
</style>