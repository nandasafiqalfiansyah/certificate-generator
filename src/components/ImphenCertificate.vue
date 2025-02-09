<template>
    <v-sheet min-height="70vh" rounded="lg" class="d-flex align-center justify-center pa-4">
      <div v-if="selectedItem && selectedItem.name === 'Imphen Certificate'">
        <div class="certificate-container">
          <div class="certificate-border">
            <div class="certificate-content">
              <!-- Logo dan Header -->
              <img src="../assets/imphnen/logo.png" alt="Imphen Logo" class="certificate-logo" />
              <h1 class="certificate-title">IMPHNEN</h1>
              <p class="certificate-subtitle">プロのプログラマー | Namun Enggan Ngoding</p>
  
              <!-- Konten Sertifikat -->
              <p class="certificate-text">Diberikan Kepada</p>
              <div id="name" contenteditable="true" class="editableDiv">Nama Peserta</div>
  
              <p class="certificate-text">Atas Partisipasi Pada Grup</p>
              <div id="grup" class="certificate-program">Ingin Menjadi Programmer Handal Namun Enggan Ngoding</div>
  
              <p class="certificate-text">Diberikan Pada Tanggal</p>
              <div id="tanggal" contenteditable="true" class="editableDiv">dd/mm/yyyy</div>
  
              <!-- Signature -->
              <div class="certificate-signature">Admin Grup</div>
              <p class="signature-text">Admin Grup</p>
  
              <!-- Footer -->
              <p class="certificate-note">*Berlaku sampai grupnya hangus</p>
            </div>
          </div>
        </div>
      </div>
      <h2 v-else class="text-h5 text-md-h4 text-lg-h3 font-weight-bold">
        {{ selectedItem ? selectedItem.name : "Pilih Sertifikat" }}
      </h2>
    </v-sheet>
  </template>
  
  <script setup lang="ts">
  import { defineProps } from "vue";
  
  const props = defineProps<{ selectedItem: { name: string; image: string | null } | null }>();
  </script>
  
  <style scoped>
  /* Styling sertifikat */
  .certificate-container {
    width: 800px;
    height: 500px;
    background: url("../assets/imphnen/bg.webp") no-repeat center center;
    background-size: cover;
    border: 10px solid #007bff;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .certificate-border {
    width: 90%;
    height: 90%;
    border: 5px solid #007bff;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  
  .certificate-content {
    text-align: center;
    width: 80%;
  }
  
  .certificate-logo {
    width: 180px;
    margin-bottom: 10px;
  }
  
  .certificate-title {
    font-size: 32px;
    font-weight: bold;
    color: #007bff;
  }
  
  .certificate-subtitle {
    font-size: 18px;
    color: #007bff;
  }
  
  .certificate-text {
    font-size: 16px;
    font-weight: bold;
    margin-top: 10px;
    color: #007bff;
  }
  
  .editableDiv {
    font-size: 20px;
    font-weight: bold;
    color: #115598;
    border-bottom: 2px solid black;
    width: 60%;
    margin: auto;
  }
  
  .certificate-program {
    font-size: 18px;
    font-weight: bold;
    color: #115598;
  }
  
  .certificate-signature {
    font-size: 25px;
    font-style: italic;
    margin-top: 20px;
    font-family: "Cursive";
    color: #000;
  }
  
  .signature-text {
    font-size: 16px;
    color: #007bff;
    
  }
  
  .certificate-note {
    font-size: 12px;
    margin-top: 15px;
    font-style: italic;
    color: dimgrey;
  }
  </style>
  