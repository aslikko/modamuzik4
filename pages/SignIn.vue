<template>
    <v-container>
        <v-row>
            <h3 style="color: dimgrey">Kayıtlı Kullanıcı Girişi</h3>
        </v-row>
        <v-row>
            <h3 style="color: dimgrey">--------------------------------------------------------------------</h3>
        </v-row>
        <v-row>
            E-Posta *
        </v-row>
        <v-row>
            <v-col cols="4" style="margin-left: -10px">
                <input type="email" v-model="email" placeholder="Email" >
            </v-col>
        </v-row>
        <v-row style="margin-top: -30px">
            Şifre *
        </v-row>
        <v-row>
            <v-col cols="4" style="margin-left: -10px">
               <input type="password" v-model="password" placeholder="Password">
            </v-col>
        </v-row>
        <v-row style="margin-top: -55px; margin-left: 120px">
            <v-checkbox
                    v-model="ex4"

                    color="black"
                    value="true"
                    hide-details>
                <template v-slot:label>
                    <span style="font-size: 12px">Beni Hatırla</span>
                </template>
            </v-checkbox>
            <span style="color: red; margin-top: 60px;font-size: 12px;margin-left: -100px">Şifrenizi mi unuttunuz?</span>
        </v-row>
        <v-row>
            <v-btn
                    style="font-size: 22px; background-color: #444; color: white; width: 260px; height: 40px;margin-top: 20px"
            >TAMAM
            </v-btn>
        </v-row>
    </v-container>
</template>

<script>
    export default {
       
        name: "SignIn",
              
        data() {
            return {
                email: "",
                password: ""
                
      }
 },
 methods: {
     login() {
         firebase.auth().signInWithEmailAndPassword(this.email, this.password).then(
             user=> {
                 alert('Oturum ok')
             },
             err=>{
                 alert('Hata'+ err)
             }
         );
     }
     
 },
}
</script>

<style scoped>

</style>