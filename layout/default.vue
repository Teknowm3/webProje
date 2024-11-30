<template>
    <div class="layout" :class="{ collapsed: isCollapsed }">
        <!-- Sol taraf: Navbar -->
        <nav class="navbar" v-if="!isCollapsed">
            <button @click="toggleNavbar" class="collapse-button">
                {{ isCollapsed ? 'Expand' : 'Collapse' }}
            </button>
            <button v-for="(button, index) in buttons" :key="index" @click="showComponent(index)" class="nav-button"
                :disabled="isCollapsed">
                {{ button }}
            </button>
        </nav>

        <!-- Sağ taraf: Main Bar -->
        <main class="main-bar">
            <!-- Aktif olan component dinamik olarak yüklenir -->
            <component :is="currentComponent" v-if="currentComponent" />

            <!-- X Butonu: Layout'a geri dön -->
            <button v-if="isCollapsed" @click="toggleNavbar" class="close-button">X</button>
        </main>
    </div>
</template>

<script setup>
import { ref, computed } from "vue";
import { defineAsyncComponent } from "vue";

// Buton isimleri
const buttons = [
    "Home Search",
    "Footer",
    "Header",
    "login-logup",
    "Component 5",
    "Component 6",
    "Component 7",
    "Component 8",
    "Component 9",
    "Component 10",
];

// Aktif componentin indeksini takip eder
const activeComponent = ref(0);

// Komponentlerin dinamik olarak yüklenmesi
const componentList = [
    defineAsyncComponent(() => import("~/components/homeSearch.vue")),
    defineAsyncComponent(() => import("~/components/footer.vue")),
    defineAsyncComponent(() => import("~/components/header.vue")),
];

// Aktif componenti hesaplar
const currentComponent = computed(() => {
    return componentList[activeComponent.value];
});

// Componenti değiştirme fonksiyonu
function showComponent(index) {
    activeComponent.value = index;
}

// Navbar'ın açık mı kapalı mı olduğunu kontrol eden ref
const isCollapsed = ref(false);

// Navbar'ı açıp kapatan fonksiyon
function toggleNavbar() {
    isCollapsed.value = !isCollapsed.value;
}
</script>

<style scoped>
.layout {
    display: flex;
    height: 100vh;
    transition: all 0.3s ease;
}

.navbar {
    width: 20%;
    background-color: #f5f5f5;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 10px;
    transition: width 0.3s ease;
}

.navbar.collapsed {
    display: none;
    /* Navbar tamamen kaybolur */
}

.nav-button {
    width: 90%;
    margin: 5px 0;
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    text-align: center;
    transition: opacity 0.3s ease;
}

.nav-button:disabled {
    opacity: 0.5;
    cursor: not-allowed;
}

.nav-button:hover {
    background-color: #0056b3;
}

.collapse-button {
    width: 90%;
    padding: 10px;
    margin: 10px 0;
    background-color: #333;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.main-bar {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #fff;
    position: relative;
    transition: margin-left 0.3s ease;
}

.main-bar.collapsed {
    margin-left: 0;
    /* Navbar gizlendiğinde, içerik alanı tam genişlikte olacak */
}

.close-button {
    position: absolute;
    top: 95%;
    left: 20px;
    padding: 10px;
    background-color: red;
    color: white;
    border: none;
    border-radius: 50%;
    cursor: pointer;
}

.close-button:hover {
    background-color: #b20000;
}
</style>