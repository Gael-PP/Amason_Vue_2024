<template>

    <component :is="currentComponent" @toggle="toggleComponent" />

</template>

<script setup>
import { ref, computed } from 'vue';
import SignInCard from '../components/SignInCard.vue';
import SignUpCard from '../components/SignUpCard.vue';

const isSignUp = ref(false);

const currentComponent = computed(() => (isSignUp.value ? SignUpCard : SignInCard));

const toggleComponent = () => {
    isSignUp.value = !isSignUp.value;
};
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Montserrat', sans-serif;
}

body {
    background-color: #c9d6ff;
    background: linear-gradient(to right, #e2e2e2, #c9d6ff);
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
}


.container {
    background-color: #fff;
    border-radius: 30px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.35);
    position:relative;
    overflow: hidden;
    width: 50vw;
    max-width: 768px;
    min-height: 70vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
    transition: width 0.3s, height 0.3s;
}



.container p {
    font-size: 1rem;
    line-height: 1.5rem;
    letter-spacing: 0.3px;
    margin: 20px 0;
}

.container button {
    background-color: #512da8;
    color: #fff;
    font-size: 0.875rem;
    padding: 10px 2.5rem;
    border: 1px solid transparent;
    border-radius: 8px;
    font-weight: 600;
    letter-spacing: 0.5px;
    text-transform: uppercase;
    margin-top: 10px;
    cursor: pointer;
    

}

.container button:hover {
    background-color: black;
    color: white;
    transition: all 0.3s;
    transform: scale(1.05);
}

.container .Enviar:hover {
    background-color: #b5c5fb;
    color: black;
    font-weight: bold;
}

.container img {
    width: 50%;
    position:absolute;
    top: 10px;
    border-radius: 25px;
    margin-top: 1.5rem;
    margin-bottom: 1rem;

}

.container form {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 0 2.5rem;
    height: 100%;
    border-radius: 10px;
    margin-top: 1rem;
}

.container input {
    background-color: #eee;
    border: none;
    margin: 8px 0;
    padding: 10px 15px;
    font-size: 1rem;
    border-radius: 8px;
    width: 100%;
    outline: none;
}

.form-container {
    margin-top: 60px;
    position: relative;
    height: 80%;
    transition: all 0.6s ease-in-out;
    display: flex;
    justify-content: center;

}

.sign {
    width: 100%;
    z-index: 2;
}

h1 {
    
    margin-bottom: 1rem;
}

@media (max-width: 1024px) {
    .container {
        width: 70vw;

    }
}

@media (max-width: 768px) {
    .container {
        width: 70vw;
        min-height: 50vh;
        padding: 15px;
    }

    .container form {
        padding: 0 20px;
    }

    .container input {
        font-size: 0.95rem;
        padding: 8px 12px;
    }
}

@media (max-width: 480px) {
    .container {
        width: 70vw;
        border-radius: 20px;
        min-height: 50vh;
        padding: 10px;
    }

    .container h1 {
        font-size: 1.25rem;
    }

    .container button {
        padding: 8px 25px;
        font-size: 0.8rem;
    }

    .container input {
        padding: 8px 10px;
    }

    .container a {
        font-size: 0.75rem;
    }
}
</style>