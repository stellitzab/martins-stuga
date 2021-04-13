<template>
    <v-row class="form-row"> 
            <v-col cols="12" md="4">
              <v-text-field
              v-model="firstname"
              :rules="nameRules"
              :counter="20"
              label="Förnamn"
              required>
              </v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
              v-model="lastname"
              :rules="nameRules"
              :counter="20"
              label="Efternamn"
              required>
              </v-text-field>
            </v-col>
            <v-col cols="12" md="4">
              <v-text-field
              v-model="email"
              :rules="emailRules"
              label="E-mail"
              required>
              </v-text-field>
            </v-col>
    </v-row>
</template>

<script>
export default {

      data: () => ({
      valid: false,
      firstname: '',
      lastname: '',
      nameRules: [
        v => !!v || 'Fyll i namn',
        v => v.length <= 15 || 'Namn måste vara kortare än 15 bokstäver, sorry alla Papastathopoulos',
      ],
      email: '',
      emailRules: [
        v => !!v || 'Fyll i giltig e-mail',
        v => /.+@.+/.test(v) || 'E-mail måste vara en giltig adress',
      ],
      loader: null,
      loading: false,
    }),
}
</script>

