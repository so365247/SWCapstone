<template>
    <div style="background-color: #2a2a2a; display: flex; justify-content: center; align-items: center; height: 100vh;">
        <div style="padding: 20px; border-radius: 10px; max-width: 400px; width: 100%; text-align: center;">
            <h3 style="color: #5cffd1; font-weight: bold; margin-bottom: 20px;">회원가입</h3>
                <v-form>
                    <v-text-field
                    label="ID"
                    color="grey"
                    style="height: 50px; background-color: #3a3a3a; color: white; margin-bottom: 30px;"
                    ></v-text-field>

                    <v-text-field
                    label="PW"
                    :append-inner-icon="visible ? 'mdi-eye-off' : 'mdi-eye'"
                    :type="visible ? 'text' : 'password'"
                    color="grey"
                    style="height: 50px; background-color: #3a3a3a; color: white; margin-bottom: 30px;"
                    @click:append-inner="togglePasswordVisibility"
                    ></v-text-field>

                    <v-text-field
                    label="E-MAIL"
                    color="grey"
                    style="height: 50px; background-color: #3a3a3a; color: white; margin-bottom: 30px;"
                    ></v-text-field>

                    <v-text-field
                    label="NAME"
                    color="grey"
                    style="height: 50px; background-color: #3a3a3a; color: white; margin-bottom: 30px;"
                    ></v-text-field>

                    <v-btn
                    color="#5cffd1"
                    medium
                    block
                    style="height: 50px; border-radius: 25px; color: black; font-weight: bold;"
                    >
                    가입
                    </v-btn>
                </v-form>
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
    togglePasswordVisibility() {
    this.visible = !this.visible;
    },
},
};
</script>

<style scoped>
.fill-height {
height: 100vh;
display: flex;
align-items: center;
justify-content: center;
}
</style>