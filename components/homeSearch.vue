<!-- Components/homeSearch.vue -->
<template>
    <div class="max-width-container">
        <img class="mainPhoto" src="~/public/main/heroxl.png" alt="background">
        <div class="photo">
            <div class="all-thing">
                <div class="text-searchBox">
                    <div class="text">
                        <h1 class="frontText">
                            Scale your professional <br /> workforce with <i>freelancers</i>
                        </h1>
                    </div>
                    <div class="searchBox">
                        <div class="searchBarPackage">
                            <form class="searchForm-searchButton">
                                <div class="inputWrapper">
                                    <input type="search" class="long-placeholder"
                                        placeholder="Search for any service..." v-model="searchQuery">
                                    <!-- Custom Cancel Button -->
                                    <button v-if="searchQuery" @click="clearSearch" class="cancel-button" type="button">
                                        ×
                                    </button>
                                    <button class="submitButton" type="submit">
                                        <img src="~/public/main/search.png" alt="search-icon"
                                            class="submit-button-icon">
                                    </button>
                                </div>
                            </form>
                        </div>
                    </div>
                </div>
                <div class="subText">
                    <span>Trusted by:</span>
                    <ul>
                        <li><img src="~/public/main/subPhotos/meta.png" alt="meta"></li>
                        <li><img src="~/public/main/subPhotos/google.png" alt="google"></li>
                        <li><img src="~/public/main/subPhotos/netflix.png" alt="netflix"></li>
                        <li><img src="~/public/main/subPhotos/pg.png" alt="pg"></li>
                        <li><img src="~/public/main/subPhotos/paypal.png" alt="paypal"></li>
                        <li><img src="~/public/main/subPhotos/payoneer.png" alt="payoner"></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
export default {
    name: 'HomeSearch',
    data() {
        return {
            searchQuery: ''
        };
    },
    methods: {
        clearSearch() {
            this.searchQuery = ''; // Clear the search query
        }
    }
};
</script>

<style scoped>
.max-width-container {
    position: relative;
    width: 100%;
    height: 100vh;
    display: flex;
    overflow: hidden;
    align-items: center;
}

.mainPhoto {
    position: absolute;
    top: 8.8%;
    left: 12.95%;
    width: 1400px;
    height: 500px;
    border-radius: 18px;
}

.photo {
    position: absolute;
    top: -10%;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}

.all-thing {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    text-align: center;
    gap: 15px;}

.text-searchBox {
    width: 100%;
    display: flex;
    position: relative;
    flex-direction: column
}

.text {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
}

.frontText {
    font-size: 60px;
    font-weight: 400;
    color: #fff;
    text-align: center;
    letter-spacing: -1.2px;
    line-height: 69px;
}

.frontText i {
    font-size: 62px;
    font-family: 'domaineDisplayItalics';
    color: #fff;
    letter-spacing: -1.55px;
    line-height: 71.3px;
}

.searchBox {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 726px;
    height: 60px;
    padding-bottom: 30px;
}

.searchBarPackage {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 610px;
    height: 100%;
    font-size: 20px;
    line-height: 24px;
    padding-left: 0;
}

.searchForm-searchButton {
    display: flex;
    align-items: center;
    width: 100%;
    height: 100%;
    position: relative;
}

.inputWrapper {
    display: flex;
    position: relative;
    width: 100%;
    height: 100%;
}

.long-placeholder {
    width: 100%;
    height: 100%;
    border: none;
    border-radius: 10px;
    font-size: 16px;
    font-weight: 400;
    color: #000;
    background-color: #fff;
    padding: 20px;
    outline: none;
    padding-right: 10px;
}

.submitButton {
    position: absolute;
    width: 48px;
    height: 48px;
    right: 6px;
    margin-top: 6px;
    border: none;
    border-radius: 10px;
    background-color: #003912;
    cursor: pointer;
    display: flex;
    text-align: center;
    justify-content: center;
    align-items: center;
}

.submitButton:hover {
    background-color: #006d3e;
}

.submit-button-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 24px;
    height: 24px;
}

.submit-button-icon img {
    width: 20px;
    height: 20px;
}

.subText {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    color: #6d8e77;
}

.subText span {
    font-size: 12px;
    font-weight: 400;
}

.subText ul {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 40px;
    list-style: none;
}

.subText ul li img {
    line-height: 24px;
    opacity: 0.5;
}

/* Custom Cancel Button */
.cancel-button {
    position: absolute;
    right: 65px;
    top: 51%;
    transform: translateY(-50%);
    background-color: #e4e5e7;
    border: none;
    border-radius: 50%;
    color: #7a7d85;
    font-size: 23px;
    cursor: pointer;
    width: 26px;
    height: 26px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.cancel-button:hover {
    background-color: #dadbdd;
}

@font-face {
    font-family: 'Macan';
    src: url('/fonts/macan/macan-regular.woff2') format('truetype');
    font-weight: normal;
    font-style: normal;
}

@font-face {
    font-family: 'domaineDisplayItalics';
    src: url('/fonts/macan/domaineDisplay-medium-italics.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
}

* {
    font-family: 'Macan';
}
</style>