<template>
    <v-container fluid>
        <div class="login-form">
            <h1 class="title">GUARDIAN</h1>

            <v-text-field label="ID" color="grey" class="input-box"></v-text-field>
            
            <v-text-field
                :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
                :type="visible ? 'text' : 'password'"
                label="PW"
                color="grey"
                class="input-box"
                @click:append-inner="togglePWvisibility"
            ></v-text-field>

            <v-btn @click.prevent="goDashBoard" class="login-btn">
                로그인
            </v-btn>

            <div class="link">
                <a href="#" class="link-txt">아이디 찾기</a> |
                <a href="#" class="link-txt">비밀번호 찾기</a> |
                <a href="#" @click.prevent="goSignUp" class="link-txt">회원가입</a>
            </div>
        </div>
    </v-container>
</template>

<style>
html, body {
    margin: 0;
    padding: 0;
    height: 100vh;
    overflow: hidden;
}

.v-application {
    margin: 0 !important;
    padding: 0 !important;
}

.v-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #2a2a2a;
}

.login-form {
    padding: 20px;
    border-radius: 10px;
    max-width: 400px;
    width: 100%;
    text-align: center;
}

.title {
    color: #5cffd1;
    font-weight: bold;
    margin-bottom: 20px;
}

.input-box {
    height: 50px;
    background-color: #3a3a3a;
    color: white;
    margin-bottom: 30px;
}

.login-btn {
    width: 400px;
    height: 50px !important;
    font-size: 14px;
    border-radius: 25px;
    color: black;
    font-weight: bold;
    background-color: #5cffd1;
}

.link {
    font-size: 12px;
    margin-top: 15px;
    color: #fff;
}

.link-txt {
    text-decoration: none;
    color: #fff;
    margin: 0 10px;
    cursor: pointer;
}
</style>

<script>
export default {
    data() {
        return {
            visible: false,
        };
    },
    methods: {
        togglePWvisibility() {
            this.visible = !this.visible;
        },
        goSignUp() {
            this.$router.push({ path: '/signup' });
        },
        goDashBoard() {
            this.$router.push({ path: '/dashboard' });
        },
    },
};
</script>
