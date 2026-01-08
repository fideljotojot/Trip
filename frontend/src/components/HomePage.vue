<script>
import amalfiImg from '@/assets/images/Italy/amalfi coast and campania/faraglioni.jpg'
import calabriaImg from '@/assets/images/Italy/calabria/Vibo-Valentia.jpg'
import liguriaImg from '@/assets/images/Italy/liguria/monterosso/Monterosso beach.jpg'
import pugliaImg from '@/assets/images/Italy/puglia/Punta Prosciutto.jpg'
import sardaniaImg from '@/assets/images/Italy/puglia/Punta Prosciutto.jpg'
import siciliaImg from '@/assets/images/Italy/puglia/Punta Prosciutto.jpg'
import toscanaImg from '@/assets/images/Italy/puglia/Punta Prosciutto.jpg'

export default {
    data() {
        return {
            user: 'Beatrix',
            selectedPage: 'Amalfi Coast',
            pages: ['Amalfi Coast' ,'Calabria','Liguria','Pugulia','Sardania','Sicilia','Toscana'],
            backgroundImages: {
                'Amalfi Coast': amalfiImg,
                'Calabria': calabriaImg,
                'Liguria': liguriaImg,
                'Pugulia': pugliaImg,
                'Sardania': sardaniaImg,
                'Sicilia': siciliaImg,
                'Toscana': toscanaImg,
            },
            images: {
                'Amalfi Coast': [
                    { name: 'Faraglioni', src: '@/assets/images/Italy/amalfi coast and campania/faraglioni.jpg' },
                    { name: 'Marina', src: '@/assets/images/Italy/amalfi coast and campania/marina.jpg' }
                ],
                'Calabria' : [
                    { name: 'Tropea', src: '@/assests/images/Italy/calabria/Vibo-Valentia.jpg' }
                ],
                'Liguria' : [
                    { name: 'Monterosso', src: '@/assets/images/Italy/liguria/monterosso/Monterosso beach.jpg' },
                    { name: 'Monterosso', src: '@/assets/images/Italy/liguria/monterosso/Monterosso sunset.jpg' },
                    { name: 'Baia del Silenzio', src: '@/assets/images/Italy/liguria/baia_del_silenzio_Sestri_Levante.jpeg' }
                ],
                'Puglia' : [
                    { name: 'Punta Proscuitto', src: '@/assets/images/Italy/puglia/Punta Prosciutto.jpg' },
                    { name: 'Baia del Silenzio', src: '@/assets/images/Italy/puglia/Torre-Sant-Andrea-near-Melendugno-Lecce-district-Apulia-Italy.jpg' }
                ],
                'Sardania' : [
                    { name: 'Punta Proscuitto', src: '@/assets/images/Italy/puglia/Punta Prosciutto.jpg' },
                    { name: 'Baia del Silenzio', src: '@/assets/images/Italy/puglia/Torre-Sant-Andrea-near-Melendugno-Lecce-district-Apulia-Italy.jpg' }
                ],
                'Sicily' : [
                    { name: 'Punta Proscuitto', src: '@/assets/images/Italy/puglia/Punta Prosciutto.jpg' },
                    { name: 'Baia del Silenzio', src: '@/assets/images/Italy/puglia/Torre-Sant-Andrea-near-Melendugno-Lecce-district-Apulia-Italy.jpg' }
                ],
                'Toscana' : [
                    { name: 'Punta Proscuitto', src: '@/assets/images/Italy/puglia/Punta Prosciutto.jpg' },
                    { name: 'Baia del Silenzio', src: '@/assets/images/Italy/puglia/Torre-Sant-Andrea-near-Melendugno-Lecce-district-Apulia-Italy.jpg' }
                ],
            }
        }
    },
    methods: {
        getBackgroundImage() {
            return this.backgroundImages[this.selectedPage];
        }
    }
}
</script>

<template>
    <main :style="{ backgroundImage: `url('${getBackgroundImage()}')`, backgroundSize: 'cover', backgroundPosition: 'center' }">
        <section class="sidebar">
            <header>Welcome, dear {{ user }}</header>
            <ul>
                <li v-for="page in pages" :key="page" @click="selectedPage = page" :class="{ active: selectedPage === page }">
                    {{ page }}
                </li>
            </ul>
        </section>
        <section>
            <RouterLink/>
        </section>
    </main>
</template>

<style scoped>
main {
    width: 100%;
    height: 100vh;
    overflow: hidden;
}

.sidebar {
    width: clamp(200px, 15%, 400px);
    height: 100vh;
    background-color: rgb(10, 61, 98, 41%);
    display: flex;
    flex-direction: column;
    gap: 1em;
    padding: 1em 0;
    color: #fff;
}

.sidebar ul {
    list-style: none;
    display: flex;
    flex-direction: column;
    text-align: center;
    padding: 0;
    gap: 4em;
    font-family: 'Libre Baskerville', serif;
}

.sidebar ul li {
    font-weight: bold;
    font-size: 1.25;
    cursor: pointer;
    padding: 0.5em 1em;
    border-radius: 4px;
    transition: background-color 0.3s ease;
}

.sidebar ul li.active {
    color: rgb(220, 56, 56);
    border-left: 3px solid #fff;
}
</style>