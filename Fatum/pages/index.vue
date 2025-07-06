<template>
    <div class="min-h-screen flex items-center justify-center">    
        <div class="text-center flex flex-col items-center justify-center">
            <button v-if="showButton" @click="Activate(), playClickSound()" class="z-50 text-white rounded transition duration-300" :style="{ opacity: isActive ? '0.0' : '1' }">
                <Antenna />
            </button>
            <div class="absolute" :style="{ opacity: toLogin ? '1' : '0.0', transition: 'opacity 1.0s ease-in-out' }">
                <h1 class="text-4xl font-semibold">Please Provide Login Data</h1>
                <input 
                    v-model="loginData" 
                    @input="playClickSound()"
                    type="text" 
                    placeholder="Enter your login data"
                    class="rounded-2xl bg-gray-700 mt-4 p-2 w-full text-center" 
                />
                <button @click="handleLogin(), playClickSound()" class="mt-4 px-6 py-2 bg-gray-700 text-white rounded-2xl hover:bg-gray-600 transition duration-300 cursor-pointer">
                    <p>Login</p>
                </button>
            </div>
        </div>
    </div>
    <button class="absolute top-10 right-10" @click="ActivateSettings(), playClickSound()">
        <Cog />
    </button>
    <div class="absolute top-20 right-10 p-6 bg-gray-700 rounded-lg transisiotn duration-300 max-w-100 text-sm" :style=" {opacity: settingsActive? '1.0' : '0.0'} ">
        <p>R3Vlc3QtUHJpb3JpdHkwCg==</p>
        <p>PASSWORD: Qui,exveniamelit.Monolitiam</p>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. <span class="hover:text-white">Qui,</span> expedita! Doloribus, earum ad, adipisci et voluptates ullam quo iusto, eos sapiente ipsum officiis nobis placeat aperiam <span class="hover:text-white">ex</span> tempore veritatis expedita.</p>
        <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aut consequatur dolore fugiat vitae quod ut libero <span class="hover:text-white">veniam</span> consequuntur similique rerum modi vel consectetur at quasi sunt ullam illo, perferendis exercitationem?</p>
        <p>Lorem, ipsum dolor sit amet consectetur adipisicing <span class="hover:text-white">elit.</span> Iusto, rerum accusantium magnam consequuntur repellendus quibusdam qui numquam, ratione pariatur laborum consectetur dolorum? <span class="hover:text-white">Monolitia</span> officiis ab deserunt assumenda recusandae adipisci veniam!</p>
        <button class="cursor-pointer transform duration-200 hover:text-white">
            <p>Privacy Settings</p>
        </button>
    </div>
</template>

<script setup>

const isActive = ref(false);
const settingsActive = ref(false);
const toLogin = ref(false);
const showButton = ref(true);
const loginData = ref('');

const Activate = () => {
    if (!isActive.value) {
        isActive.value = true;
        setTimeout(() => {
            showButton.value = false;
            toLogin.value = true;
        }, 300);
    }
}

const ActivateSettings = () => {
    settingsActive.value = !settingsActive.value;
}

const handleLogin = () => {
    console.log('Login attempted with:', loginData.value);
    if (loginData.value.trim() == "R3Vlc3QtUHJpb3JpdHkwCg==") { // Guest-Priority0
        navigateTo({
            path: '/transition',
            query: { level: 'Auth-0'}
        });
    } else {

    }
}

const playClickSound= () => {
    const audio = new Audio('/sounds/click.mp3');
    audio.play().catch(error => {
        console.error('Error playing sound:', error);
    });
}

</script>