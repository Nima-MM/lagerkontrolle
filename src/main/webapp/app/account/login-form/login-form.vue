<template>
  <v-card
    class="mx-auto h-50"
    color="surface-variant"
    image="transparent"
    max-width="1768"
    subtitle="Sie haben noch keinen Zugang?"
    title="Anmeldung"
  >
    &nbsp;<router-link class="alert-link" to="/register">Registrieren Sie sich</router-link>
    <template v-slot:actions>
      <v-sheet class="mx-auto" width="300">
        <v-form fast-fail @submit.prevent>
          <!-- <v-text-field v-model="login" :rules="firstNameRules" label="Login"></v-text-field> -->
          <v-text-field type="email" v-model="login" label="Benutzername"></v-text-field>
          <v-text-field type="password" v-model="password" label="Passwort"></v-text-field>
          <v-checkbox v-model="rememberMe" color="info" :label="`Angemeldet bleiben? ${rememberMe.toString()}`"></v-checkbox>
          <v-btn class="mt-2" type="submit" @click="doLogin" block>Anmelden</v-btn>
        </v-form>
      </v-sheet>
    </template>
  </v-card>
</template>
<script lang="ts" src="./login-form.component.ts"></script>

<!-- <template>
  <div class="modal-body">
    <div class="row justify-content-center">
      <div class="col-md-8">
        <b-alert show data-cy="loginError" variant="danger"
          v-if="authenticationError"><strong>Anmeldung fehlgeschlagen!</strong> Überprüfen Sie bitte
          Ihre Angaben und versuchen Sie es erneut.</b-alert>
      </div>
      <div class="col-md-8">
        <b-form @submit.prevent="doLogin()">
          <b-form-group label="Benutzername" label-for="username">
            <b-form-input id="username" type="text" name="username" autofocus
              placeholder="Ihr Benutzername" v-model="login" data-cy="username">
            </b-form-input>
          </b-form-group>
          <b-form-group label="Passwort" label-for="password">
            <b-form-input id="password" type="password" name="password" placeholder="Ihr Passwort"
              v-model="password" data-cy="password">
            </b-form-input>
          </b-form-group>
          <b-form-checkbox id="rememberMe" name="rememberMe" v-model="rememberMe" checked>
            <span>Automatische Anmeldung</span>
          </b-form-checkbox>
          <div>
            <b-button data-cy="submit" type="submit" variant="primary">Anmelden</b-button>
          </div>
        </b-form>
        <p></p>
        <div>
          <b-alert show variant="warning">
            <b-link :to="'/account/reset/request'" class="alert-link"
              data-cy="forgetYourPasswordSelector">Sie haben Ihr Passwort vergessen?</b-link>
          </b-alert>
        </div>
        <div>
          <b-alert show variant="warning">
            <span>Sie haben noch keinen Zugang?</span>
            <b-link :to="'/register'" class="alert-link">Registrieren Sie sich</b-link>
          </b-alert>
        </div>
      </div>
    </div>
  </div>
</template> -->
