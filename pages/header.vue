<template>
    <header class="header">
        <!-- Logo -->
        <div class="logo-container">
            <a href="/header">
                <img src="/logo.png" alt="Fiverr Logo" class="logo" />
            </a>
        </div>
        <!-- Menü -->
        <nav class="nav">
            <ul>
                <!-- Fiverr Pro -->
                <div class="fiverr-dropdown" @click.stop="toggleDropdown('fiverrPro')">
                    <a href="#" class="fiverr-dropdown-toggle">Fiverr Pro <img
                            v-bind:class="{ 'rotate-arrow': activeDropdown === 'fiverrPro' }"
                            src="/header/kArrowDown.png" alt="Arrow Down" class="arrow-icon" /></a>
                    <div v-if="activeDropdown === 'fiverrPro'" class="fiverr-dropdown-menu">
                        <div class="fiverr-pro-box">
                            <div v-for="(block, index) in fiverrProItems" :key="index" class="dropdown-block"
                                @click="navigateTo(block.path)">
                                <div class="inner-block">
                                    <div class="icon">
                                        <img :src="block.icon" alt="Icon" />
                                    </div>
                                    <div class="text">
                                        <strong>{{ block.title }}</strong>
                                        <p>{{ block.description }}</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- Explore -->
                <li class="dropdown" @click.stop="toggleDropdown('explore')">
                    <a href="#" class="dropdown-toggle">Explore <img
                            v-bind:class="{ 'rotate-arrow': activeDropdown === 'explore' }" src="/header/kArrowDown.png"
                            alt="Arrow Down" class="arrow-icon" />
                    </a>
                    <div v-if="activeDropdown === 'explore'" class="dropdown-menu">
                        <div v-for="item in exploreItems" :key="item.title" class="dropdown-item">
                            <a :href="item.path">
                                <strong>{{ item.title }}</strong>
                                <p>{{ item.description }}</p>
                            </a>
                        </div>
                    </div>
                </li>
                <li @click="openLanguageModal" style="margin-top: -2px;"><a href="#">🌏︎ English</a></li>
                <li><a href="/header">Become a Seller</a></li>
                <li><a href="/header">Sign in</a></li>
                <li><a href="/header" class="nav-join">Joın</a></li>
            </ul>
        </nav>
        <!-- Modal -->
        <div v-if="isModalVisible" class="overlay" @click.self="closeModal">
            <div class="modal">
                <div class="modal-header">
                    <h2>Select your preferences</h2>
                    <!-- Close Button: Placed at the top right corner of the modal -->
                    <button class="close-btn" @click="closeModal">X</button>
                </div>
                <div class="tabs">
                    <div class="tab" :class="{ active: activeTab === 'Language' }" @click="setActiveTab('Language')">
                        Language
                    </div>
                    <div class="tab" :class="{ active: activeTab === 'Currency' }" @click="setActiveTab('Currency')">
                        Currency
                    </div>
                    <div class="active-underline"></div> <!-- Green underline -->
                </div>
                <div class="divider"></div> <!-- Gray divider -->
                <div class="tab-content">
                    <ul v-if="activeTab === 'Language'">
                        <li v-for="language in languages" :key="language"
                            :class="{ selected: selectedLanguage === language }" @click="selectLanguage(language)">
                            <span v-if="selectedLanguage === language" class="tick">✔</span>
                            <span v-else class="tick-space"></span> <!-- Empty space for tick -->
                            {{ language }}
                        </li>
                    </ul>
                    <ul v-if="activeTab === 'Currency'">
                        <li v-for="currency in currencies" :key="currency.name"
                            :class="{ selected: selectedCurrency === currency.name }"
                            @click="selectCurrency(currency.name)">
                            <span class="currency-name">{{ currency.name }}</span>
                            <span class="currency-symbol">{{ currency.symbol }}</span>
                            <span v-if="selectedCurrency === currency.name" class="tick">✔</span>
                            <span v-else class="tick-space"></span>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </header>
</template>

<script lang="ts">
import { defineComponent, type ImgHTMLAttributes } from "vue";

export default defineComponent({
    data() {
        return {
            isModalVisible: false,
            activeDropdown: null as string | null, // Hangi dropdown'ın açık olduğunu tutar
            activeTab: "Language",
            selectedLanguage: "English",
            selectedCurrency: "United States Dollar",
            languages: ["English", "Deutsch", "Español", "Français", "Português", "Italiano", "Nederlands"],
            currencies: [
                { name: "United States Dollar", symbol: "USD - $" },
                { name: "Euro", symbol: "EUR - €" },
                { name: "British Pound", symbol: "GBP - £" },
                { name: "Australian Dollar", symbol: "AUD - A$" },
                { name: "Canadian Dollar", symbol: "CAD - CA$" },
                { name: "Turkish New Lira", symbol: "TRY - TRY" },
                { name: "Japanese Yen", symbol: "JPY - ¥" },
                { name: "United Arab Emirates Dirham", symbol: "AED - AED" },
                { name: "Malasian Ringgit", symbol: "MYR - MYR" },
                { name: "Mexican Peso", symbol: "MXN - MX$" },
                { name: "Pakistani Rupee", symbol: "PKR - PKR" }
            ],
            isExploreDropdownVisible: false,
            exploreItems: [
                { title: "Answers", description: "Powered by AI, answered by Fiverr freelancers", path: "/answers" },
                { title: "Community", description: "Connect with Fiverr’s team and community", path: "/community" },
                { title: "Guides", description: "In-depth guides covering business topics", path: "/guides" },
                { title: "Podcast", description: "Inside tips from top business minds", path: "/podcast" },
                { title: "Learn", description: "Professional online courses, led by experts", path: "/learn" },
                { title: "Blog", description: "News, information and community stories", path: "/blog" },
                { title: "Logo Maker", description: "Create your logo instantly", path: "/logo-maker" },
                { title: "Login", description: "Access your account", path: "/login" }
            ],
            // Fiverr Pro Dropdown İçeriği
            isFiverrProDropdownVisible: false,
            // Fiverr Pro content with image paths
            fiverrProItems: [
                {
                    title: "I'm looking to hire",
                    description: "My team needs vetted freelance talent and a premium business solution.",
                    icon: '/fiverpro1.png',
                    path: '/header'
                },
                {
                    title: "I want to offer Pro services",
                    description: "I’d like to work on business projects as a Pro freelancer or agency.",
                    icon: '/fiverpro2.png', // Another image path
                    path: '/main'
                }
            ],
        };
    },
    methods: {
        openLanguageModal() {
            this.isModalVisible = true;
        },
        closeModal() {
            this.isModalVisible = false;
        },
        setActiveTab(tab: string) {
            this.activeTab = tab;
        },
        selectLanguage(language: string) {
            this.selectedLanguage = language;
        },
        selectCurrency(currency: string) {
            this.selectedCurrency = currency;
        },
        // Fiverr Pro Dropdown'u Toggle Et
        toggleFiverrProDropdown() {
            this.isFiverrProDropdownVisible = !this.isFiverrProDropdownVisible;
        },
        // Explore Dropdown'u Toggle Et
        toggleExploreDropdown() {
            this.isExploreDropdownVisible = !this.isExploreDropdownVisible;
        },
        toggleDropdown(dropdown: string) {
            this.activeDropdown = this.activeDropdown === dropdown ? null : dropdown;
        },
        closeDropdown() {
            this.activeDropdown = null;
        },
    },
    mounted() {
        // Document click event listener ekle
        document.addEventListener("click", this.closeDropdown);
    },
    beforeUnmount() {
        // Event listener'ı kaldır
        document.removeEventListener("click", this.closeDropdown);
    },
});
</script>

<style scoped>
.header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 14px 151px;
    padding-bottom: 22.3px;
    background-color: #ffffff;
    color: black;
    box-shadow: inset 0 -0.7px 0 0 #e0e0e0;
}

.logo-container {
    flex: 1;
}

.logo {
    height: 24.3px;
}

.nav ul {
    display: flex;
    gap: 40px;
    list-style-type: none;
    margin: 0;
    height: 20px;
    font-size: 14px;
    padding-right: 20px;
}

.nav a {
    text-decoration: none;
    color: #62646f;
    /* Varsayılan renk: koyu gri */
    font-weight: bold;
}

.nav a:hover {
    color: #1dbf73;
    /* Hover (üstüne gelindiğinde) renk: Fiverr yeşili */
}

.nav .nav-join {
    background-color: white;
    color: #1dbf73;
    box-shadow: #1dbf73;
    border: 1px solid #1dbf73;
    padding: 8px 16px;
    border-radius: 5px;
}

.nav .nav-join:hover {
    background-color: #1dbf73;
    color: white;
}

.overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
    overflow-x: hidden;
}

.modal {
    background: white;
    padding: 20px;
    width: 500px;
    height: 375px;
    border-radius: 6px;
    box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.2);
    overflow-x: hidden;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
}

.tabs {
    display: flex;
    justify-content: flex-start;
    gap: 10px;
    margin-bottom: 10px;
}

.tab {
    cursor: pointer;
    padding: 7px 10px;
    position: relative;
    font-weight: bold;
    transition: color 0.3s ease;
    color: #62646f;
}

.tab.active {
    color: #1dbf73;
    border-bottom: 1.7px solid #1dbf73;
}

.active-underline {
    position: flex;
    bottom: 0;
    height: 2px;
    background-color: #1dbf73;
    transition: left 0.3s ease, width 0.3s ease;
}

.tab-content {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: left;
    gap: 10px;
    height: 100%;
    overflow-y: auto;
    padding-right: 10px;
    padding-top: 10px;
}

.tab-content ul {
    list-style: none;
    padding: 0;
    margin: 0;
    overflow-x: hidden;
    word-wrap: break-word;
    max-width: 100%;
}

.tab-content li {
    display: flex;
    padding: 6px;
    font-size: 17px;
    cursor: pointer;
    align-items: center;
    gap: 16px;
    transition: background-color 0.3s;
    position: relative;
}

.tab-content .currency-item {
    display: flex;
    flex-direction: column;
    /* Stack name vertically */
}


.tab-content li:hover {
    background-color: #f0f0f0;
    /* Add a light gray background on hover */
    width: 100%;
    /* Ensure it covers from left to right */
}

.selected {
    color: #62646a;
}

.tick {
    transform: translateX(-50%);
    font-size: 0.6rem;
    position: relative;
    color: #62646a;
    z-index: 1;
}

.tick-space {
    display: inline-block;
    width: 20px;
    margin-left: -12.34px;
    /* Space where the tick would be */
}

.divider {
    height: 1px;
    background-color: #e0e0e0;
    width: 100%;
    margin: -10px 0 0 0;
}

.currency-name {
    color: #62646f;
    /* Dark gray for the currency name */
    flex-grow: 1;
    flex: 1;
    /* Allow space for tick */
}

.currency-symbol {
    color: #b0b0b0;
    flex: 1;
    /* Light gray for the currency symbol */
}

.tab-content ul li:hover {
    background-color: #f5f5f5;
    /* Gray background on hover */
    width: 100%;
    /* Ensure it covers from left to right */
}

.modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 0px;
    margin-top: -20px;
    margin-left: 8px;
    font-size: 14px;
}

.close-btn {
    background: none;
    border: none;
    font-size: 16px;
    color: #62646f;
    cursor: pointer;
}

.nav li:nth-child(2) a:hover {
    color: #62646a;
    background-color: #fafafa;
    border-radius: 0px;
    outline: 8px solid #fafafa;
    /* Outline ile arka planı büyütme */
}

.dropdown {
    position: relative;
}

.dropdown-menu {
    position: absolute;
    background-color: white;
    border: 1px solid #e0e0e0;
    box-shadow: 0 0.2px 0.2px rgba(0, 0, 0, 0.1);
    border-radius: 4px;
    min-width: 280px;
    max-width: 400px;
    z-index: 1000;
    padding: 10px 0;
    /* İçeriklere biraz boşluk ekledik */
    display: block;
    /* Menü öğelerinin alt alta sıralanmasını sağlar */
    margin-left: -15px;
    left: 0;
    margin-top: 10px;
}

.dropdown-item {
    padding: 10px 8px;
    font-size: 14px;
    cursor: pointer;
    transition: background-color 0.3s;
    display: flex;
    flex-direction: column;
}

.dropdown-item p {
    font-weight: normal;
    /* Normal font */
    color: #62646f;
    /* Açık gri */
    margin: 5px 0 0 0;
    /* Üstten biraz boşluk */
    font-size: 13px;
    /* Daha küçük font boyutu */
}

.dropdown-item.hover {
    background-color: #f0f0f0;
}

.dropdown-item strong {
    font-weight: bold;
    /* Kalın font */
    color: black;
    /* Siyah renkte */
}

.fiverr-dropdown {
    position: relative;
}

.fiverr-dropdown-toggle {
    position: relative;
    font-weight: bold;
    cursor: pointer;
    text-decoration: none;
    color: black;
    /* Siyah renkte sabit kalması için */
    padding: 10px;
    margin-top: -10px;
    border: 1px solid transparent;
    border-radius: 6px;
    transition: all 0.3s;
    align-items: center;
    /* Dikeyde ortalar */
}

.nav .fiverr-dropdown-toggle {
    color: black;
    /* Varsayılan renk yeşil */
    font-weight: bold;
    /* Varsayılan yazı ağırlığı */
    display: flex;
    align-items: center;
    /* Dikeyde ortalama */
    justify-content: center;
    /* Yatayda ortalama */
    gap: 2px;
}

.nav .fiverr-dropdown-toggle:hover {
    color: black;
    /* Hover durumunda siyah */
    font-weight: bold;
    /* Hover durumunda kalın */
}

.fiverr-dropdown-toggle:hover {
    background-color: #e0e0e0;
    border: 1px solid #e0e0e0;
    color: black;
    /* Renk değişmesin */
    font-weight: bold;
    /* Bold olarak kalsın */
}

.fiverr-dropdown-menu {
    position: absolute;
    top: 27px;
    /* Menünün açılacağı yerin konumu */
    left: 0;
    background-color: #fff;
    border: 1px solid #ccc;
    box-shadow: 0px 1px 1px rgba(0, 0, 0, 0.2);
    border-radius: 2px;
    z-index: 1000;
    width: 300px;
    /* Menü genişliği */
    padding: 10px;
}

.fiverr-pro-box {
    display: flex;
    flex-direction: column;
    margin-bottom: -10px;
}

.dropdown-block {
    margin-bottom: 10px;
    display: flex;
    align-items: left;
    border-bottom: 1px solid #e0e0e0;
    padding: 0px 0;
    cursor: pointer;
    outline: 1px solid #e0e0e0;
    border-radius: 2px;
    /* Outline ekle */
    background-color: white;
    /* Arka plan beyaz olsun */

}

.dropdown-block:hover {
    background-color: #f9f9f9;
    /* Hover durumunda hafif gri ton */
}

.dropdown-block strong {
    display: block;
    font-size: 14px;
    font-weight: bold;
}

.dropdown-block p {
    font-size: 12px;
    color: #666;
    margin-top: 10px;
}

.icon {
    flex-shrink: 0;
    /* Resim sıkışmasın */
    margin-right: 10px;
    size: 10px;
}

.icon img {
    width: 50px;
    height: 50px;
}

.text {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    overflow: hidden;
    /* Uzun metin taşmasın */
}

.text strong {
    font-size: 14px;
    font-weight: bold;
}

.text p {
    font-size: 12px;
    color: #666;
    margin-top: 5px;
}

.inner-block {
    display: flex;
    align-items: center;
    padding: 10px;
    width: 100%;
}

.dropdown-toggle {
    display: flex;
    align-items: center;
    justify-content: center;
    gap:2px;
}

.arrow-icon {
    width: 20px;
    /* Ok simgesinin boyutu */
    height: 20px;
    transition: transform 0.5s ease;
    /* 1 saniyede dönüş animasyonu */
}

/* Ok simgesi dönsün, dropdown açıkken */
.rotate-arrow {
    transform: rotate(180deg);
}
</style>