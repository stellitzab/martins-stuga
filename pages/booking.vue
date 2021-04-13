<template>
<div class="booking">
  <v-container>
    <h1>Boka er vistelse här</h1>
  </v-container>
  <v-container class="form">
    <form id="booking-form">
        <v-container>
          <v-row v-for="person in persons" :key="person.name">
            <v-col cols="12" md="3">
              <label>Förnamn </label>
              <input type="text" name="persons[][name]" class="form-textfield" placeholder="Förnamn">
            </v-col>
            <v-col cols="12" md="3">
              <label>Efternamn </label>
              <input type="text" name="persons[][lastname]" class="form-textfield" placeholder="Efternamn">
            </v-col>
            <v-col cols="12" md="3">
              <label>E-mail</label>
              <input type="email" name="persons[][email]" class="form-textfield" placeholder="E-mail">
            </v-col>
          </v-row>
          <v-col cols="12" md="3">
            <v-btn 
            rounded
            color="#C4C4C4"
            @click="removePerson"
            class="">
            <v-icon>
              mdi-minus
            </v-icon>
            Ta bort           
            </v-btn>
          <v-btn
            @click="addNewPerson"
            color="#8C9DB0"
            rounded
            >
            <v-icon>
              mdi-plus
            </v-icon>
              Lägg till person
          </v-btn>
          </v-col>
        </v-container>
        <v-row>
          <h2>
            Gemensamma tillval
          </h2>
          <v-col cols="12">
              <v-row>
                <v-col cols="12" md="4" class="checkboxes">
                  <div>
                    <label>
                      Öl + vinpaketet
                    </label>
                    <input type="checkbox">
                  </div>
                  <div>
                    <label>
                      Viltpaketet
                    </label>
                    <input type="checkbox">
                  </div>
                  <div>
                    <label>
                      Helpension
                    </label>
                    <input type="checkbox">
                  </div>
                </v-col>
                <v-col cols="12" md="4">
                  <v-combobox
                    v-model="select"
                    :items="items"
                    label="Önskemål om aktiviteter"
                    multiple chips
                    color="primary">
                    <template v-slot:selection="data">
                      <v-chip
                        color="primary"
                      >
                        {{ data.item }}
                      </v-chip>
                    </template>
                    </v-combobox>
                </v-col>
                <v-col cols="12" md="2">
                  <label for="date">Ankomstdatum:</label>
                  <input type="date" id="arrive-date" name="date">
                </v-col>
                <v-col cols="12" md="2">
                  <label for="date">Hemresedatum:</label>
                  <input type="date" id="depart-date" name="date">
                </v-col>
              </v-row>
            <p>
              <v-btn 
              class="book"
              type="submit"
              disabled
              rounded
              large
              color='#5f6061'
              @click="displayError"
              >Skicka in
              </v-btn>
            </p>
          </v-col>
        </v-row>
    </form>
  </v-container>
  <div>
    <fire-icon>
    </fire-icon>
  </div>
</div>
</template>

<style scoped>
  .v-form {
    font-family: 'Poppins';
  }
  .booking {
    background-size: cover;
  }
  h1 {
    color: "primary";
    font-weight: lighter;
  }

  h2 {
    font-family: 'Nunito Sans';
    color: "primary";
    font-weight: lighter;
  }

  .submit-button {
    border-radius: 28px;
    background-color: #5f6061;
    height: 52px;
    min-width: 92px;
    padding: 0 23.1111111111px;
    color: white;
    font-family: "Poppins";
    font-weight: bold;
  }

  .form-textfield {
    padding: 4px;
    font-size: 16px;
    border-bottom: 2px solid #244e77;
  }

  label {
    font-family: 'Poppins';
    font-weight: 700;
  }

  .checkboxes {
    display: grid;
    place-content: center;
  }

</style>

<script>

import bookingform from '~/components/BookingForm'
import fireicon from '~/components/FireIcon'

export default {

  components: {
    bookingform,
    fireicon,
  },
  data()
    {
    return {
        person:
        {
          name: '',
          lastname: '',
          email: '',
        },
        persons: [],
        index: 0,
        items: [
          'Slackline',
          'Fiske',
          'Lektion i norrbottnisk patriotism',
          'Dart',
          'Skjuta pilbåge',
          'Åka båt'
        ],
    }
  },
  
  methods: {

      displayError: function () {
        alert('Förlåt, det går inte att boka i dagsläget!');
      },
      addNewPerson() {
        this.persons.push({name: this.person.name, lastname: this.person.lastname, email: this.person.email});
      },
      removePerson(index) {
        if(this.persons.length == 1) {
          alert('Minst en person måste finnas i bokningen!')
        }
        else {
          this.persons.pop();
        }
      }

    },
  
  mounted: function () {
    this.persons = [{ "name": "stella", "lastname": "biliou", "email": "stella12@mail.se"}];
  },
}
</script>