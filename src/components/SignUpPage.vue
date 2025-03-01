<template>
    <v-icon class="back" @click="$router.go(-1)">mdi-chevron-left</v-icon>
    <v-container fluid>
        <div class="signup-form">
            <h3 class="title">회원가입</h3>
            <v-form>
                <v-text-field label="ID" color="grey" class="input-box"></v-text-field>

                <v-text-field 
                    label="PW" 
                    :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'" 
                    :type="visible ? 'text' : 'password'"
                    color="grey" 
                    class="input-box"
                    @click:append-inner="togglePasswordVisibility"
                ></v-text-field>

                <v-text-field label="E-MAIL" color="grey" class="input-box"></v-text-field>
                
                <v-text-field label="NAME" color="grey" class="input-box"></v-text-field>
                
                <v-btn class="signup-btn" @click="submitForm">
                    가입
                </v-btn>
            </v-form>
        </div>
    </v-container>
</template>

<style>
html, body {
    margin: 0 !important;
    padding: 0 !important;
    height: 100vh !important;
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

.signup-form {
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

.signup-btn {
    width: 400px;
    height: 50px !important;
    font-size: 14px;
    border-radius: 25px;
    color: black;
    font-weight: bold;
    background-color: #5cffd1;
}

.back {
    position: fixed;
    top: 50px;
    left: 80px;
    font-size: 24px;
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
        togglePasswordVisibility() {
            this.visible = !this.visible;
        },
        submitForm() {
            console.log('가입 시도');
        },
    },
};
</script>
