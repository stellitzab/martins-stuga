<template>
  <v-container class="footer">
      <v-row align="center"
      justify="center" class="credits">
        <strong> © Stella Biliou </strong> &nbsp; {{ new Date().getFullYear() }}
      </v-row>
  </v-container>
</template>

<style scoped>

    .footer {
    min-height: 200px;
    background-color: #1A1F28;
    background-image: url('~assets/trees.svg');
    background-repeat: repeat-x;
    min-width: 100%;
    color: white;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    }
    
    </style>

<script>
export default {

    data: () => ({
      icons: [
        'mdi-home',
        'mdi-email',
        'mdi-calendar',
        'mdi-delete',
      ],
      items: [
        'default',
        'absolute',
        'fixed',
      ],
      padless: false,
      variant: 'default',
    }),
}
</script>