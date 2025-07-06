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
        <p>PASSWORD: <span class="hover:text-white">LaudantiumdolorilloEligendihic</span></p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. <span class="hover:text-white">Laudantium</span> nam, asperiores recusandae fuga alias amet necessitatibus in, quae, similique excepturi vero unde magni quasi corporis veritatis mollitia! Obcaecati, velit. Porro.</p>
        <p>Lorem ipsum <span class="hover:text-white">dolor</span> sit, amet consectetur adipisicing elit. Doloremque repellendus rem eligendi similique quisquam repudiandae quaerat incidunt quis adipisci est placeat, consequatur <span class="hover:text-white">illo</span> possimus fugiat corrupti voluptas, obcaecati, earum vel.</p>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. <span class="hover:text-white">Eligendi</span>, iste consequatur minima aut nam placeat reprehenderit. Nesciunt quae cum voluptate temporibus ipsum <span class="hover:text-white">hic</span> praesentium unde illum doloribus culpa, magni distinctio!</p>
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
    if (loginData.value.trim() == "LaudantiumdolorilloEligendihic") { // Guest-Priority0
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