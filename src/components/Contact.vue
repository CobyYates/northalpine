<template>
  <v-container fluid class="px-0 mx-0 pb-0">
    <v-parallax src="https://scontent-den4-1.xx.fbcdn.net/v/t1.0-9/119461834_10224969756250740_3395514406448708858_o.jpg?_nc_cat=109&_nc_sid=e3f864&_nc_ohc=GRn_s1LTOJ4AX9fXLJ0&_nc_ht=scontent-den4-1.xx&oh=b5cfc4b609199573d84b33a288588e99&oe=5F9F8B48">
    <v-overlay absolute>
      <v-form v-model="valid">
        <v-container>
          <v-row>
            <v-col cols="12" sm="12" md="12" lg="8" xl="8" class="mx-auto">
              <v-row>
                <v-col cols="12 py-0" sm="6" md="6" lg="6" xl="6">
                  <v-text-field
                    v-model="firstname"
                    solo
                    :rules="nameRules"
                    label="First name"
                    required
                  ></v-text-field>
                </v-col>

                <v-col cols="12 py-0" sm="6" md="6" lg="6" xl="6">
                  <v-text-field
                    v-model="lastname"
                    solo
                    :rules="nameRules"
                    label="Last name"
                    required
                  ></v-text-field>
                </v-col>

                <v-col cols="12 py-0" sm="12" md="12" lg="12" xl="12">
                  <v-text-field
                    v-model="email"
                    solo
                    :rules="emailRules"
                    label="E-mail"
                    required
                  ></v-text-field>
                </v-col>
                <v-col cols="12 py-0" sm="12" md="12" lg="12" xl="12">
                  <v-textarea
                    v-model="message"
                    solo
                    label="Message"
                    required
                  ></v-textarea>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-form>
      </v-overlay>
    </v-parallax>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    valid: false,
    firstname: "",
    lastname: "",
    message: "",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => v.length <= 10 || "Name must be less than 10 characters",
    ],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+/.test(v) || "E-mail must be valid",
    ],
  }),
};
</script>

<style></style>
