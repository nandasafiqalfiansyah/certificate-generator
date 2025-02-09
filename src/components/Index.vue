<script setup lang="ts">
import { ref, onMounted } from "vue";
import Certificate from "../components/ImphenCertificate.vue"; 
import bgImage from "../assets/imphnen/bg.webp";
import * as htmlToImage from "html-to-image";

const certificates = ref([
  { name: "Imphen Certificate", image: bgImage },
]);

const selectedCertificate = ref<{ name: string; image: string | null } | null>(certificates.value[0]);

const refreshPage = () => {
  selectedCertificate.value = certificates.value[0];
};

const downloadCertificate = () => {
  const certificateElement = document.getElementById("certificate-display");
  if (!certificateElement) return;

  htmlToImage.toPng(certificateElement)
    .then((dataUrl) => {
      const link = document.createElement("a");
      link.href = dataUrl;
      link.download = "certificate.png";
      link.click();
    })
    .catch((error) => {
      console.error("Error saat mengunduh sertifikat:", error);
    });
};
</script>

<template>
  <v-main class="bg-grey-lighten-3">
    <v-container fluid>
      <v-row>
        <!-- Sidebar List -->
        <v-col cols="12" md="3" lg="2">
          <v-sheet rounded="lg">
            <v-list rounded="lg">
              <v-list-item
                v-for="(certificate, index) in certificates"
                :key="index"
                :title="certificate.name"
                link
                @click="selectedCertificate = certificate"
              ></v-list-item>

              <v-divider class="my-2"></v-divider>
              <v-list-item color="grey-lighten-4" title="Refresh" link @click="refreshPage"></v-list-item>
              <v-list-item color="grey-lighten-4" title="Download Sertifikat" link @click="downloadCertificate"></v-list-item>
            </v-list>
          </v-sheet>
        </v-col>
        <!-- Content Display -->
        <v-col cols="12" md="9" lg="10" class="content-wrapper">
          <div id="certificate-display" class="certificate-container">
            <Certificate :selectedItem="selectedCertificate" />
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-main>
</template>

<style scoped>
.content-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 80vh;
  width: 100%;
}

.certificate-container {
  width: 100%;
  overflow-x: auto;
  display: flex;
  justify-content: center;
  padding: 10px;
}
</style>
