<script>
export default {
    data() {
        return {
            user: 'Beatrix'
        }
    }
}
</script>

<template>
    <main>
        <header>Welcome, dear {{ user }}</header>
        <section class="sidebar">
            <ul>
                <li>Amalfi and Campania</li>
                <li>Calabria</li>
                <li>Liguria</li>
                <li>Pugulia</li>
                <li>Sardania</li>
                <li>Sicilia</li>
                <li>Toscana</li>
            </ul>
        </section>
    </main>
</template>

<style scoped>

</style>