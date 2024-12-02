<template>
    <div class="signIn-golge">
        <div class="sign">
            <!-- Image Container -->
            <div class="img-container">
                <img src="/login/login.png" alt="loginPng" />
                <div class="font-on-image">
                    <h2>Success starts here</h2>
                    <ul class="features">
                        <li><span>✔</span> Over 700 categories</li>
                        <li><span>✔</span> Quality work done faster</li>
                        <li><span>✔</span> Access to talent and businesses <br />
                            <div style="padding-left: 15px;"> across the globe</div>
                        </li>
                    </ul>
                </div>
            </div>
            <div v-if="isLoginVisible" class="login-container">
                <div>
                    <div class="bosluk"></div>
                    <section class="header-login-section">
                        <div class="header-login-container">
                            <h4>{{ type === 'login' ? 'Sign in to your account' : 'Create a new account' }}</h4>
                            <span v-if="type === 'login'">
                                Don't have an account?
                                <span @click="typeAction" class="link">Join here</span>
                            </span>
                            <span v-else>
                                Already have an account?
                                <span @click="typeAction" class="link">Sign in</span>
                            </span>
                        </div>
                        <div class="signIn-buttons">
                            <button class="google-btn">
                                <img src="~/public/login/google.png" alt="Google Icon" />
                                <span>Continue with Google</span>
                            </button>
                            <button @click="showEmailLogin" class="email-btn">
                                <img src="~/public/login/mail.png" alt="mail Icon" />
                                <span>
                                    {{ type === 'login' ? 'Continue with email/username' : 'Continue with email' }}
                                </span>
                            </button>
                        </div>
                        <div class="separator">
                            <span>OR</span>
                        </div>
                        <div class="social-buttons">
                            <button class="apple-btn">
                                <img src="/login/apple.png" alt="Apple Icon" />
                                <span>Apple</span>
                            </button>
                            <button class="facebook-btn">
                                <img src="/login/facebook.png" alt="Facebook Icon" />
                                <span>Facebook</span>
                            </button>
                        </div>
                    </section>
                    <section class="end-of-login">
                        <p class="footer">
                            By joining, you agree to the Fiverr
                            <a href="#" class="link">Terms of Service</a> and to occasionally receive
                            emails from us. Please read our
                            <a href="#" class="link">Privacy Policy</a> to learn how we use your personal
                            data.
                        </p>
                    </section>
                </div>
            </div>
            <div v-else class="Login1">
                <div class="bosluk"></div>
                <div>
                    <button @click="goBackToLogin" class="back-btn">
                        <img src="/login/goBack.png" alt="Back Icon" class="back-icon" />
                        <span>Back </span>
                    </button>
                </div>
                <div>
                    <section>
                        <div class="login2-title">
                            <h4>
                                <span v-if="type === 'login'">Continue with your email or <br />username</span>
                                <span v-else>Continue with your email</span>
                            </h4>
                        </div>
                    </section>
                    <div class="field">
                        <section class="field-label">
                            <label for="login">Email</label>
                        </section>
                        <div class="field-input">
                            <input type="email" name="email" id="email" v-model="email" @blur="validateEmail"
                                :class="{ 'error-outline': !isValid }" placeholder="name@email.com">
                            <img v-if="!isValid" src="~/public/login/uyari.png" alt="Warning Icon"
                                class="warning-icon" />
                            <p v-if="!isValid" class="error-message">Looks like this email is incomplete</p>
                        </div>
                        <section class="field-label">
                            <label for="login">Password</label>
                        </section>
                        <div class="field-input">
                            <input :type="passwordVisible ? 'text' : 'password'" name="password" id="password"
                                v-model="password" />
                            <img :src="passwordVisible ? '/login/see.png' : '/login/cantSee.png'" alt="eye icon"
                                class="eye-icon" @click="togglePasswordVisibility" />
                        </div>
                    </div>
                    <section class="end-of-login">
                        <div>
                            <button class="continue-btn">
                                <span>Continue</span>
                            </button>
                        </div>
                        <div v-if="type !== 'login'" class="bosluk2"></div>
                        <p class="footer" :style="{ marginTop: `${footerPadding}` }">
                            By joining, you agree to the Fiverr
                            <a href="#" class="link">Terms of Service</a> and to occasionally receive
                            emails from us. Please read our
                            <a href="#" class="link">Privacy Policy</a> to learn how we use your personal
                            data.
                        </p>
                    </section>
                </div>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from 'vue';

export default defineComponent({
  setup() {
    const isLoginVisible = ref(true); // Başlangıçta login-container görünür
    const type = ref("login");
    const email = ref(""); // Kullanıcının girdiği e-posta
    const isValid = ref(true); // E-posta doğruluğunu kontrol etmek için
    const passwordVisible = ref(false); // Şifrenin görünürlüğünü kontrol etmek için
    const password = ref(""); // Kullanıcının girdiği şifre

    const footerPadding = computed(() => {
      // Eğer e-posta geçerli değilse, padding ekle
      return isValid.value ? '171px' : '138px';
    });

    // Methods
    const showEmailLogin = () => {
      // Email Login ekranını göster
      isLoginVisible.value = false;
    };

    const goBackToLogin = () => {
      // Ana login ekranına dön
      isLoginVisible.value = true;
    };

    const typeAction = () => {
      // Login ve Join ekranları arasında geçiş
      type.value = type.value === 'login' ? 'join' : 'login';
    };

    const validateEmail = () => {
      // Basit e-posta doğrulama
      const emailRegex: RegExp = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      isValid.value = emailRegex.test(email.value);
    };

    const togglePasswordVisibility = () => {
      // Şifrenin görünür olup olmadığını değiştirme
      passwordVisible.value = !passwordVisible.value;
    };

    return {
      isLoginVisible,
      type,
      email,
      isValid,
      passwordVisible,
      password,
      footerPadding,
      showEmailLogin,
      goBackToLogin,
      typeAction,
      validateEmail,
      togglePasswordVisibility,
    };
  },
});
</script>


<style scoped>
.signIn-golge {
    background-color: rgba(64, 65, 69, 0.6);
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
    display: flex;
    justify-content: center;
    align-items: center;
}

.sign {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    margin: 0;
    border-radius: 12px;
}

/* Image Container */
.img-container {
    width: 100%;
    max-width: 437.5px;
    height: auto;
    max-height: 645px;
    position: relative;
    z-index: 2;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
}

.img-container img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    /* Görüntüyü taşıma olmadan kırpar */
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;
}

.font-on-image {
    position: absolute;
    top: -10px;
    left: -10px;
    padding: 40px 50px;
    color: white;
    z-index: 3;
}

.font-on-image h2 {
    font-size: 32px;
    font-weight: 700;
    margin-bottom: 20px;
    line-height: 38.4px;
}

.features {
    list-style-type: none;
    padding: 0;
    color: white;
}

.features li {
    margin: 13px 0;
    font-size: 18px;
    font-weight: 400;
    line-height: 26px;
}

.features span {
    color: #ffffff;
    justify-content: center;
    font-size: 14px;
}

/* Login Form Styles */
.login-container {
    background-color: white;
    width: 437.5px;
    height: 645px;
    display: flex;
    flex-direction: column;
    position: relative;
    right: 0;
    box-sizing: border-box;
    z-index: 4;
    overflow-y: none;
    padding: 20px;
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
}

.bosluk {
    display: flex;
    padding-top: 20px;
}

.bosluk2 {
    display: flex;
    padding-top: 31px;
}

.header-login-section {
    display: flex;
    flex-direction: column;
    text-align: left;
    padding: 0px 20px;
    width: 90%;
    gap: 0px;
}

.header-login-container {
    display: flex;
    flex-direction: column;
    text-align: left;
    padding-bottom: 50px;
}

.header-login-container h4 {
    font-size: 24px;
    font-weight: 700;
    margin-bottom: 5px;
    color: #222325;
    line-height: 31.2px;
}

.header-login-container span {
    font-size: 16px;
    color: #222325;
    line-height: 24px;
}

.header-login-container span .link {
    color: #595a5b;
    cursor: pointer;
    text-decoration: underline;
}

.signIn-buttons {
    display: flex;
    flex-direction: column;
    gap: 10px;
    line-height: 24px;
}

.signIn-buttons button {
    width: 100%;
    height: 42px;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-family: "Macan", sans-serif;
    font-size: 16px;
    font-weight: 700;
    display: flex;
    align-items: center;
    gap: 25px;
    background-color: white;
}

.signIn-buttons button:hover {
    cursor: pointer;
    background-color: #f5f5f5;
}

.signIn-buttons button span {
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    width: 100%;
}

.signIn-buttons button img {
    align-items: center;
    left: 20px;
    width: 24px;
    height: 24px;
}

.signIn-buttons button:last-child {
    margin-bottom: 20px;
}

.separator {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 12px;
    color: #999999;
    text-align: center;
    margin-bottom: 20px;
}

.social-buttons {
    display: flex;
    justify-content: space-between;
    width: 100%;
    line-height: 24px;
}

.social-buttons button {
    width: 49%;
    height: 42px;
    border: 1px solid #ddd;
    border-radius: 4px;
    display: flex;
    align-items: center;
    gap: 8px;
    background-color: white;
}

.social-buttons button img {
    align-items: center;
    left: 40px;
    width: 24px;
    height: 24px;
}

.social-buttons button span {
    font-size: 16px;
    font-weight: 700;
    justify-content: center;
    display: flex;
    align-items: center;
    text-align: center;
    width: 100%;
}

.social-buttons button:hover {
    cursor: pointer;
    background-color: #f5f5f5;
}

.end-of-login {
    height: 240px;
    display: flex;
    flex-direction: column;
    left: 0;
    bottom: 0;
    width: 100%;
    text-align: start;
    vertical-align: baseline;
}

.end-of-login p {
    height: 100%;
    text-align: start;
    vertical-align: baseline;
    margin-top: 43%;
    box-sizing: border-box;
}

.footer {
    text-align: start;
    font-size: 12px;
    color: #74767E;
    width: 94%;
    padding-left: 22px;
    line-height: 20px;
}

.footer a {
    color: #74767E;
    cursor: pointer;
    text-decoration: underline;
}

/** Login */
.Login1 {
    background-color: white;
    width: 437.5px;
    height: 645px;
    display: flex;
    flex-direction: column;
    position: relative;
    right: 0;
    box-sizing: border-box;
    z-index: 4;
    overflow-y: none;
    padding: 20px;
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
}

.back-btn {
    display: flex;
    align-items: center;
    gap: 5px;
    cursor: pointer;
    padding: 0;
    background: none;
    border: none;
}

.back-btn:hover {
    background: none;
}

.back-btn span {
    font-size: 14px;
    font-weight: 700;
    color: #222325;
}

.back-icon {
    width: auto;
    height: 12px;
}

.login2-title {
    display: flex;
    flex-direction: column;
    text-align: left;
    width: 91%;
    gap: 0px;
    overflow: hidden;
}

.login2-title h4 {
    padding: 0 20px;
    font-size: 24px;
    font-weight: 700;
    margin-bottom: 25px;
    color: #222325;
    line-height: 31.2px;
}

.field {
    display: flex;
    flex-direction: column;
    text-align: left;
    padding: 0;
    width: 90%;
    gap: 0px;
}

.field-label {
    display: flex;
    flex-direction: column;
    text-align: left;
    padding: 0 20px;
    width: 90%;
    gap: 0px;
}

.field-label label {
    font-size: 16px;
    font-weight: 700;
    margin-bottom: 5px;
    line-height: 24px;
}

.field-input {
    display: flex;
    flex-direction: column;
    text-align: left;
    padding: 0 20px;
    width: 100%;
    padding-bottom: 15px;
}

.field-input input {
    width: 100%;
    height: 42px;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-family: "Macan", sans-serif;
    font-size: 16px;
    font-weight: 500;
    display: flex;
    align-items: center;
    gap: 20px;
    padding-left: 10px;
    background-color: white;
    color: #333;
}

.field-input input:focus {
    outline-color: #999999;
    color: #333;
}

.field-input input::placeholder {
    color: #C5C6C9;
    font-weight: 400;
    font-size: 16px;
}

.field-input input.error-outline {
    outline: 1px solid red;
}

.warning-icon {
    position: absolute;
    margin-top: 8px;
    right: 35px;
    width: 28px;
    height: 28px;
}

.error-message {
    color: red;
    font-size: 14px;
    font-weight: 400;
    margin-top: 5px;
}

.eye-icon {
    position: absolute;
    right: 33.3px;
    margin-top: 7px;
    cursor: pointer;
    width: 28px;
    height: 28px;
}

.continue-btn {
    width: 93%;
    margin-top: 30px;
    margin-left: 20px;
    margin-bottom: -55px;
    height: 42px;
    background-color: #f1f1f1;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-family: "Macan", sans-serif;
    font-size: 16px;
    font-weight: 700;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    color: rgba(51, 51, 51, 0.3);
    background-color: rgba(215, 214, 214, 0.3);
}

.google-btn {
    background-color: #f1f1f1;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-family: "Macan", sans-serif;
    font-size: 16px;
    font-weight: 700;
    gap: 5px;
    padding: 0 20px;
    background-color: white;
}

.email-btn {
    background-color: #f1f1f1;
    border: 1px solid #ddd;
    border-radius: 4px;
    font-family: "Macan", sans-serif;
    font-size: 16px;
    font-weight: 700;
    gap: 5px;
    padding: 0 20px;
    background-color: white;
}

.apple-btn {
    background-color: #f1f1f1;
    border: 1px solid #ddd;
    cursor: pointer;
    border-radius: 4px;
    font-family: "Macan", sans-serif;
    font-size: 16px;
    font-weight: 700;
    gap: 5px;
    padding: 0 20px;
    background-color: white;
}

.facebook-btn {
    background-color: #f1f1f1;
    border: 1px solid #ddd;
    cursor: pointer;
    border-radius: 4px;
    font-family: "Macan", sans-serif;
    font-size: 16px;
    font-weight: 700;
    gap: 5px;
    padding: 0 20px;
    background-color: white;
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
