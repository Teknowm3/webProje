<template>
    <div class="service-container">
        <div>
            <h2>Vontélle’s go-to services</h2>
        </div>
        <div class="service-cards">
            <div class="service-card">
                <img src="~/public/services/3D-Industrial-Design_2x.png" alt="3D Industrial Design" />
                <p>3D Industrial Design</p>
            </div>
            <div class="service-card">
                <img src="~/public/services/E-commerce-Website-Development_2x.png"
                    alt="E-commerce Website Development" />
                <p>E-commerce <br /> Website Development</p>
            </div>
            <div class="service-card">
                <img src="~/public/services/Email-Marketing_2x.png" alt="Email Marketing" />
                <p>Email Marketing</p>
            </div>
            <div class="service-card">
                <img src="~/public/services/Press-Releases_2x.png" alt="Press Releases" />
                <p>Press Releases</p>
            </div>
            <div class="service-card">
                <img src="~/public/services/Logo-Design_2x.png" alt="Logo Design" />
                <p>Logo Design</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.service-container {
    text-align: center;
    margin: 20px;
    position: relative; /* Container'a relative konum ekleyelim */
}

h2 {
    font-size: 28px;
    font-weight: 400;
    position: flex; /* Konumu kontrol edebilmek için absolute */
    transform: translateX(-38%); 
    margin-bottom: 50px; 
}

.service-cards {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
    gap: 27px;
    position: relative; /* Kartlar container'ına relative konum ekleyelim */
}

.service-card {
    background: #fff;
    padding: 30px;
    border-radius: 15px;
    text-align: center;
    cursor: pointer;
    height: 120px;
    width: 200px;
    box-shadow: 0 2px 4px 2px rgba(0, 0, 0, 0.1);
}

/* Hover durumu */
.service-card:hover {
    box-shadow: 0 2px 4px 2px rgba(0, 0, 0, 0.13); /* Belirginleşen gölge */
}

.service-card img {
    height: 80px;
    width: 80px;
    border-radius: 5px;
    margin-top: -10px;
}

.service-card p {
    margin-top: 10px;
    font-weight: bold;
    font-size: 16px;
    color: #333;
    line-height: 1.5;
}

@font-face {
    font-family: 'Macan';
    src: url('/fonts/macan/macan-regular.woff2') format('truetype');
    font-weight: normal;
    font-style: normal;
}

* {
    font-family: 'Macan';
}
</style>