<template>
    <div style="background-color: #2a2a2a; display: flex; justify-content: center; align-items: center; height: 100vh;">
        <div style="padding: 20px; border-radius: 10px; max-width: 400px; width: 100%; text-align: center;">
            <h1 style="color: #5cffd1; font-weight: bold; margin-bottom: 20px;">GUARDIAN</h1>
                <v-text-field
                    label="ID"
                    color="grey"
                    style="height: 50px; background-color: #3a3a3a; color: white; margin-bottom: 30px;"
                ></v-text-field>
        
                <v-text-field
                    :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
                    :type="visible ? 'text' : 'password'"
                    label="PW"
                    color="grey"
                    style="height: 50px; background-color: #3a3a3a; color: white; margin-bottom: 30px;"
                    @click:append-inner="visible = !visible"
                ></v-text-field>
        
                <v-btn
                    color="#5cffd1"
                    style="height: 50px; border-radius: 25px; color: black;"
                    block
                >
                    login
                </v-btn>
        
                <div style="font-size: 12px; margin-top: 15px; color: #5cffd1;">
                    <a href="#" style="text-decoration: none; color: #5cffd1; margin-right: 10px;">아이디 찾기</a> |
                    <a href="#" style="text-decoration: none; color: #5cffd1; margin-left: 10px; margin-right: 10px;">비밀번호 찾기</a> |
                    <a href="#" @click.prevent="goSingUp" style="text-decoration: none; color: #5cffd1; margin-left: 10px;">회원가입</a>
                </div>
        </div>
    </div>
</template>

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
    },
    methods: {
        goSingUp() {
            this.$router.push({ path: '/signup'});
        },
    },
};
</script>