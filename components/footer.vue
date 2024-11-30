<template>
    <div id="footer">
        <!-- Divider aligned with the categories -->
        <hr class="footer-divider" />

        <!-- Footer content container -->
        <div class="footer-container">
            <!-- Footer content with 1440px max width -->
            <div class="footer-wrapper">
                <div class="footer-sections">
                    <div class="footer-section">
                        <h6>Categories</h6>
                        <ul>
                            <li><a href="/categories/graphics-design">Graphics & Design</a></li>
                            <li><a href="/categories/digital-marketing">Digital Marketing</a></li>
                            <li><a href="/categories/writing-translation">Writing & Translation</a></li>
                            <li><a href="/categories/video-animation">Video & Animation</a></li>
                            <li><a href="/categories/music-audio">Music & Audio</a></li>
                            <li><a href="/categories/programming-tech">Programming & Tech</a></li>
                            <li><a href="/categories/ai-services">AI Services</a></li>
                            <li><a href="/categories/consulting">Consulting</a></li>
                            <li><a href="/categories/data">Data</a></li>
                            <li><a href="/categories/business">Business</a></li>
                            <li><a href="/categories/personal-growth">Personal Growth & Hobbies</a></li>
                            <li><a href="/categories/photography">Photography</a></li>
                            <li><a href="/categories/finance">Finance</a></li>
                            <li><a href="/categories/end-to-end-projects">End-to-End Projects</a></li>
                            <li><a href="/categories/service-catalog">Service Catalog</a></li>
                        </ul>
                    </div>
                    <div class="footer-section">
                        <h6>For Clients</h6>
                        <ul>
                            <li><a href="/how-fiverr-works">How Fiverr Works</a></li>
                            <li><a href="/customer-success-stories">Customer Success Stories</a></li>
                            <li><a href="/trust-safety">Trust & Safety</a></li>
                            <li><a href="/quality-guide">Quality Guide</a></li>
                            <li class="fiverr-group">
                                <a href="/learn" class="main-link">Fiverr Learn</a>
                                <a href="/learn" class="sub-link">Online Courses</a>
                            </li>
                            <li><a href="/fiverr-guides">Fiverr Guides</a></li>
                            <li><a href="/fiverr-answers">Fiverr Answers</a></li>
                        </ul>
                    </div>
                    <div class="footer-section">
                        <h6>For Freelancers</h6>
                        <ul>
                            <li><a href="/become-fiverr-freelancer">Become a Fiverr Freelancer</a></li>
                            <li><a href="/become-agency">Become an Agency</a></li>
                            <li><a href="/kickstart">Kickstart</a></li>
                            <li><a href="/community-hub">Community Hub</a></li>
                            <li><a href="/forum">Forum</a></li>
                            <li><a href="/events">Events</a></li>
                        </ul>
                    </div>
                    <div class="footer-section">
                        <h6>Business Solutions</h6>
                        <ul>
                            <li><a href="/fiverr-pro">Fiverr Pro</a></li>
                            <li><a href="/project-management-service">Project Management Service</a></li>
                            <li class="fiverr-group">
                                <a href="/#" class="main-link">ClearVoice</a>
                                <a href="/#" class="sub-link">Content Marketing</a>
                            </li>
                            <li class="fiverr-group">
                                <a href="/#" class="main-link">Working Not Working</a>
                                <a href="/#" class="sub-link">Creative Talent</a>
                            </li>
                            <li class="fiverr-group">
                                <a href="/#" class="main-link">AutoDS</a>
                                <a href="/#" class="sub-link">Dropshipping Tool</a>
                            </li>
                            <li><a href="/fiverr-logo-maker">Fiverr Logo Maker</a></li>
                            <li><a href="/contact-sales">Contact Sales</a></li>
                        </ul>
                    </div>
                    <div class="footer-section">
                        <h6>Company</h6>
                        <ul>
                            <li><a href="/about-fiverr">About Fiverr</a></li>
                            <li><a href="/help-support">Help & Support</a></li>
                            <li><a href="/social-impact">Social Impact</a></li>
                            <li><a href="/careers">Careers</a></li>
                            <li><a href="/terms-service">Terms of Service</a></li>
                            <li><a href="/privacy-policy">Privacy Policy</a></li>
                            <li><a href="/partnerships">Partnerships</a></li>
                            <li><a href="/creator-network">Creator Network</a></li>
                            <li><a href="/affiliates">Affiliates</a></li>
                            <li><a href="/invite-friend">Invite a Friend</a></li>
                            <li><a href="/press-news">Press & News</a></li>
                            <li><a href="/investor-relations">Investor Relations</a></li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- Divider aligned with categories -->
            <hr class="footer-divider" />

            <!-- Footer Bottom (logolar ve metin) -->
            <div class="footer-bottom">
                <div class="footer-bottom-content">
                    <!-- Fiverr logosu en solda -->
                    <div class="footer-logos-left">
                        <img src="/public/footer/fiverrL.png" alt="Logo 1" />
                        <p style="padding-top: 7px;">© Fiverr International Ltd. 2024</p>
                    </div>

                    <!-- TikTok ve sosyal medya logoları en sağda -->
                    <div class="footer-logos-right">
                        <a href="https://www.tiktok.com" target="_blank" class="social-icon">
                            <img src="/public/footer/tiktok.png" alt="TikTok Logo" />
                        </a>
                        <a href="https://www.instagram.com" target="_blank" class="social-icon">
                            <img src="/public/footer/instagram.png" alt="Instagram Logo" />
                        </a>
                        <a href="https://www.linkedin.com" target="_blank" class="social-icon">
                            <img src="/public/footer/linkedin.png" alt="LinkedIn Logo" />
                        </a>
                        <a href="https://www.facebook.com" target="_blank" class="social-icon">
                            <img src="/public/footer/facebook.png" alt="Facebook Logo" />
                        </a>
                        <a href="https://www.pinterest.com" target="_blank" class="social-icon">
                            <img src="/public/footer/pinterest.png" alt="Pinterest Logo" />
                        </a>
                        <a href="https://www.x.com" target="_blank" class="social-icon">
                            <img src="/public/footer/x.png" alt="X Logo" />
                        </a>
                        <div>

                            <!-- Language Button -->
                            <button class="lan-button" id="language-button" @click="showLanguageModal = true">
                                🌏︎ {{ selectedLanguage }}
                            </button>

                            <!-- Modal Overlay (semi-transparent background) -->
                            <div v-if="showLanguageModal" class="language-modal-overlay" @click="closeModal">
                                <div class="language-modal" @click.stop>
                                    <!-- Close Button -->
                                    <div>
                                        <button class="close-modal" @click="closeModal">×</button>

                                        <!-- Choose Language Title -->
                                        <h2 class="modal-title">Choose Language</h2>
                                    </div>
                                    <!-- Language Options -->
                                    <div class="language-options-container">
                                        <ul class="language-list">
                                            <li v-for="(language, index) in languages" :key="index">
                                                <input type="radio" :id="language" :name="language"
                                                    v-model="selectedLanguage" :value="language"
                                                    class="language-radio" />
                                                <label :for="language">
                                                    <!-- Tick symbol when selected -->
                                                    <span v-if="selectedLanguage === language" class="tick">✔</span>
                                                    {{ language }}
                                                </label>
                                            </li>
                                        </ul>
                                    </div>
                                </div>
                            </div>
                            <!-- Currency Button -->
                            <button class="currency-button" @click="showCurrencyModal = true">
                                {{ selectedCurrency.symbol }} {{ selectedCurrency.code }}
                            </button>

                            <!-- Currency Modal (transparan gri arka plan) -->
                            <div v-if="showCurrencyModal" class="currency-modal-overlay" @click="closeCurrencyModal">
                                <div class="currency-modal" @click.stop>
                                    <!-- Close Button -->
                                    <div class="currency-modal-padding">
                                        <button class="close-modal" @click="closeCurrencyModal">×</button>
                                        <!-- Choose Currency Title -->
                                        <h2 class="modal-title">Choose a currency</h2>
                                    </div>

                                    <!-- Currency Options -->
                                    <ul class="currency-list">
                                        <li v-for="currency in currencies" :key="currency.code"
                                            @click="selectCurrency(currency)">
                                            <div class="currency-item">
                                                <!-- Tick işareti -->
                                                <span v-if="selectedCurrency.code === currency.code"
                                                    class="currency-tick">✔</span>
                                                <!-- Para birimi detayları -->
                                                <div class="currency-details">
                                                    <strong>{{ currency.name }}</strong><br />
                                                    <span class="currency-code">{{ currency.code }} - {{ currency.symbol
                                                        }}</span>
                                                </div>
                                            </div>
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </div>
                        <button class="access-button">
                            <img src="/public/footer/access.png" alt="Logo 7" />
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
interface Currency {
    name: string;
    symbol: string;
    code: string;
}

export default {
    data() {
        return {
            showLanguageModal: false,  // Controls the visibility of the modal
            selectedLanguage: 'English',  // Default language
            languages: ["English", "Deutsch", "Español", "Français", "Português", "Italiano", "Nederlands"], // List of languages
            showCurrencyModal: false, // Currency modal kontrolü
            selectedCurrency: { symbol: "$", code: "USD", name: "United States Dollar" }, // Varsayılan seçili para birimi
            currencies: [
                { name: "United States Dollar", symbol: "$", code: "USD" },
                { name: "Euro", symbol: "€", code: "EUR" },
                { name: "British Pound", symbol: "£", code: "GBP" },
                { name: "Japanese Yen", symbol: "¥", code: "JPY" },
                { name: "Canadian Dollar", symbol: "CA$", code: "CAD" },
                { name: "Australian Dollar", symbol: "A$", code: "AUD" },
                { name: "Turkish New Lira", symbol: "TRY", code: "TRY" },
                { name: "United Arab Emirates Dirham", symbol: "AED", code: "AED" },
                { name: "Malasian Ringgit", symbol: "MYR", code: "MYR" },
                { name: "Mexican Peso", symbol: "MX$", code: "MXN" },
                { name: "Pakistani Rupee", symbol: "PKR", code: "PKR" }
            ] as Currency[], // Currencies list defined with the 'Currency' interface
        };
    },
    methods: {
        closeModal() {
            this.showLanguageModal = false;  // Close modal when clicked outside or on close button
        },
        closeCurrencyModal() {
            this.showCurrencyModal = false; // Modal'ı kapatır
        },
        selectCurrency(currency: Currency) {
            this.selectedCurrency = currency;
            this.closeCurrencyModal(); // Para birimi seçildiğinde modal'ı kapat
        },
    },
};
</script>


<style scoped>
#footer {
    background: #fff;
    padding: 60px 0;
    color: #333;
    width: 100%;
}

.footer-divider {
    margin-left: 0px;
    border: 0;
    border-top: 1px solid #ddd;
}

.footer-container {
    max-width: 1440px;
    margin: 0 auto;
    padding-left: 20px;
}

.footer-wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}

.footer-sections {
    display: flex;
    flex-wrap: wrap;
    gap: 55px;
    width: 100%;
}

.footer-section {
    flex: 1;
    min-width: 200px;
}

/**Gurplaşmalar */
.fiverr-group a {
    text-decoration: none;
    color: #000;
    display: block;
    /* Alt alta görünmeleri için */
}

.fiverr-group .sub-link {
    font-size: 0.9em;
    color: #c0c3d2;
    margin-left: 0px;

}

.fiverr-group:hover .main-link,
.fiverr-group:hover .sub-link {
    text-decoration: underline;
    /* Hover durumunda ikisinin altını çiz */
}

/** Font section */
.footer-section h6 {
    font-size: 1.1rem;
    margin-bottom: 20px;
}

.footer-section ul {
    list-style: none;
    padding: 0;
}

.footer-section ul li {
    margin-bottom: 25px;
    /* Boşluk */
}

.footer-section ul li a {
    color: #757784;
    text-decoration: none;
}

.footer-section ul li a:hover {
    text-decoration: underline;
}

.footer-bottom {
    margin-top: 10px;
    text-align: center;
}

.footer-bottom-content {
    display: flex;
    justify-content: space-between;
    align-items: center;

}

.footer-logos-left,
.footer-logos-right {
    display: flex;
    gap: 12px;
    align-items: center;
}

.footer-logos-left {
    justify-content: flex-start;
}

.footer-logos-right {
    justify-content: flex-end;
}

.footer-logos-left img {
    height: 40px;
    width: auto;
}

.footer-logos-right img {
    height: 30px;
    width: auto;
}

.footer-bottom p {
    font-size: 1rem;
    color: #838e97;
    font-size: 14px;
}

.social-icon {
    display: inline-flex;
    justify-content: center;
    align-items: center;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    background-color: transparent;
    transition: background-color 0.3s ease;
    text-decoration: none;
}

.social-icon img {
    transition: transform 0.3s ease;
}

.social-icon:hover {
    background-color: rgba(0, 0, 0, 0.1);
}

/* BUTONN */
#language-button {
    cursor: pointer;
    padding: 10px 15px;
    background-color: transparent;
    color: #74767e;
    font-size: 16px;
    transition: all 0.3s ease;
    width: 140px;
    text-align: left;
    margin-right: 10px;
    border: none;
    border-radius: 0;
    outline: none;
}

#language-button:hover {
    color: black;
    background-color: #f1f1f1;
    border-radius: 50px;
    font-weight: 600;
}

.language-modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
}

.language-modal {
    background-color: white;
    padding: 0px;
    border-radius: 8px;
    width: 400px;
    height: 412px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    text-align: left;
    position: relative;
}

.close-modal {
    position: absolute;
    top: 23px;
    right: 20px;
    font-size: 28px;
    background: none;
    border: none;
    color: #333;
    cursor: pointer;
}

.language-list {
    list-style: none;
    padding: 0;
    margin: 0;
}

.language-list li {
    display: block;
    width: 92.5%;
    align-items: center;
    padding-left: 30px;
    position: relative;
}

.language-list li input {
    display: none;
}

.language-list li label {
    display: flex;
    line-height: 1.8;
    padding-left: 30px;
    cursor: pointer;
    display: flex;
    align-items: center;
}

.language-list li label::before {
    content: "";
    position: absolute;
    left: 0;
    width: 20px;
    height: 20px;
}

.language-list li .tick {
    width: 18px;
    height: 18px;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 10px;
    color: grey;
    font-size: 18px;
}

.language-list li input:checked+label {
    left: 0;
    padding-left: 10px;
    /* Tick geldiğinde boşluğu kaldır <--------------*/
}

.language-list li input:checked+label .tick {
    content: "✔";
}

.language-list li:not(:checked) .tick {
    content: "";
    /* Seçilmeyenlerde boş alan */
    margin-left: -9px;
}

.language-item {
    display: flex;
    align-items: center;
    margin: 10px 0;
    position: relative;
    padding-left: 30px;
    /* Space for the tick and radio button */
}

.language-item .tick {
    position: absolute;
    left: 0;
    /* Position the tick at the far left */
    color: green;
    font-size: 18px;
}

.language-item .language-text {
    padding-left: 10px;
    /* Space for the tick to align */
}

.language-list li label {
    display: flex;
    align-items: center;
    cursor: pointer;
    padding: 5px;
    padding-left: 29px;
    /* Tick ya da boşluk için varsayılan alan */
    position: relative;
    transition: background-color 0.2s ease;
}

.language-list li:hover {
    background-color: #f0f0f0;
}

/** Language header ı ayalıyom */
.language-modal .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.modal-title {
    padding-top: 10px;
    padding-left: 30px;
    font-size: 1.15rem;
    padding-bottom: 10px;
}

/**CURRENCY BUTTON*/
.currency-button {
    cursor: pointer;
    padding: 10px 20px;
    background-color: transparent;
    color: #74767e;
    font-size: 16px;
    width: 120px;
    text-align: left;
    border-radius: 50px;
    transition: background-color 0.3s;
    outline: none;
    border: none;
}

.currency-button:hover {
    color: black;
    background-color: #f1f1f1;
    border-radius: 50px;
    font-weight: 600;
}

.currency-modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.6);
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1000;
}

.currency-modal {
    background-color: white;
    padding: 0px;
    border-radius: 2px;
    width: 400px;
    height: 470px;
    overflow-y: auto;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    position: relative;
    display: inline-block;
    text-align: left;
}

.modal-title {
    font-size: 1.2rem;
    margin-bottom: 10px;
}

.currency-item {
    display: flex;
    align-items: center;
    position: relative;
    padding-left: 50px;
}

.currency-list {
    list-style: none;
    padding-left: 0px;
    margin: 0;
}

.currency-item .currency-tick {
    position: absolute;
    left: 0;
    color: #bbb;
    font-size: 16px;
    padding: 20px;
}

.currency-list ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

.currency-list li {
    padding: 6px 0;
    display: flex;
    align-items: center;
    cursor: pointer;
}

.currency-list li:hover {
    background-color: #f0f0f0;
}

.currency-list li input {
    display: none;
}

.currency-list li .currency-item {
    display: flex;
    align-items: center;
    width: 100%;
}

.currency-list li .currency-code {
    font-size: 14px;
    color: #8a8daa;
}

.currency-details {
    line-height: 1.4;
}

.access-button {
    border: none;
    background: none;
    padding: 10px;
    cursor: pointer;
    border-radius: 50%;
}

.access-button:hover {
    background-color: rgba(0, 0, 0, 0.1);
}

@font-face {
    font-family: 'Macan';
    src: url('/fonts/macan/macan-regular.woff2') format('truetype');
    font-weight: normal;
    font-style: normal;
}

#footer * {
    font-family: Macan;
}
</style>