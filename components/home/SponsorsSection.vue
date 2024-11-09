<template>
  <v-container fluid >
    <v-row>
      <v-col md="12">
        <h1>Our Sponsors</h1>
        <p>Sponsors dedicated to building remarkable experience!</p>
        <h2>To be our sponsore mail here:- devfestgdgdurgapur@gmail.com</h2>
        <button
        scoped style="padding: 0.5rem 1.5rem;
  background-color: #D3D3D3;
  color: #ffffff;
  font-weight: 600;
  border-radius: 0.5rem; 
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  outline: none;
  cursor: pointer;
  transition: background-color 0.2s, box-shadow 0.2s;"
    
    @click="handleRegister"
    class="register-button"
  >
    mail here
  </button>
  

        <v-container fluid class="pa-0 mt-4">
          <CommonSponsorInfo />
        </v-container>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
</script>

<style>
</style>