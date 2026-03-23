<script>
import GenstandCard from './GenstandCard.vue'

export default {
    name: 'GenstandPage',
    components: {
        GenstandCard
    },
    data() {
        return {
            // Mock-data - falske genstande til at teste kortet med
            items: [
                {
                    id: 1,
                    title: 'Boremaskine',
                    category: 'Elektronik',
                    brand: 'Bosch',
                    status: 'Tilgængelig',
                    image: 'https://placehold.co/64x64'
                },
                {
                    id: 2,
                    title: 'Cykel',
                    category: 'Sport',
                    brand: null,
                    status: 'Udlånt',
                    image: 'https://placehold.co/64x64'
                },
                {
                    id: 3,
                    title: 'Hammer',
                    category: 'Værktøj',
                    brand: 'Stanley',
                    status: 'Inaktiv',
                    image: 'https://placehold.co/64x64'
                }
            ]
        }
    }
}
</script>

<template>
    <main class="page">

        <!-- Sidetitel -->
        <h1 class="page-title">Dine genstande</h1>

        <!-- Liste af kort -->
        <div class="card-list">
            <!-- Loop gennem genstande og vis et kort for hver -->
            <GenstandCard
                v-for="item in items"
                :key="item.id"
                :title="item.title"
                :category="item.category"
                :brand="item.brand"
                :status="item.status"
                :image="item.image"
            />
        </div>

    </main>
</template>

<style scoped>

/* Page background */
.page {
    background: #f5f3ef;
    min-height: 100vh;
    padding: 24px 16px;
}

/* Page title */
.page-title {
    font-family: 'Newsreader', serif;
    font-size: 28px;
    font-weight: 600;
    color: #2d2b2a;
    margin-bottom: 24px;
    text-align: center;
}

/* Cards stacked vertically with gap between them */
.card-list {
    display: flex;
    flex-direction: column;
    gap: 12px;
}

</style>