<template>
  <NuxtLayout name="default">
    <v-container fluid class="mt-5">
      <v-row>
        <v-col md="12">
          <h1>Team</h1>
          <p>
            Our mission is to equip our community members with practical skills,
            enabling them to communicate their insights and drive innovative
            solutions effectively.
          </p>
        </v-col>
      </v-row>

      <!-- Organizer Team -->
      <v-row v-if="organizerTeam.length">
        <v-col md="12">
          <h2>Organizer Team</h2>
        </v-col>
        <v-col md="2" sm="3" cols="6" v-for="(item, index) in organizerTeam" :key="index">
          <common-team-card :data="item" />
        </v-col>
      </v-row>

      <!-- Web Team -->
      <v-row v-if="webTeam.length">
        <v-col md="12">
          <h2>Web Team</h2>
        </v-col>
        <v-col md="2" sm="3" cols="6" v-for="(item, index) in webTeam" :key="index">
          <common-team-card :data="item" />
        </v-col>
      </v-row>

      <!-- Design Team -->
      <v-row v-if="designTeam.length">
        <v-col md="12">
          <h2>Design Team</h2>
        </v-col>
        <v-col md="2" sm="3" cols="6" v-for="(item, index) in designTeam" :key="index">
          <common-team-card :data="item" />
        </v-col>
      </v-row>

      <!-- Outreach Team -->
      <v-row v-if="outreachTeam.length">
        <v-col md="12">
          <h2>Outreach Team</h2>
        </v-col>
        <v-col md="2" sm="3" cols="6" v-for="(item, index) in outreachTeam" :key="index">
          <common-team-card :data="item" />
        </v-col>
      </v-row>
    </v-container>
  </NuxtLayout>
</template>

<script setup>
const { teamData, mainData } = useJSONData();

const organizerTeam = computed(() => teamData.filter(member => member.teamCategory === 'Organizer'));
const webTeam = computed(() => teamData.filter(member => member.teamCategory === 'Web'));
const designTeam = computed(() => teamData.filter(member => member.teamCategory === 'Design'));
const outreachTeam = computed(() => teamData.filter(member => member.teamCategory === 'Outreach'));

definePageMeta({
  layout: false,
});

useSeoMeta({
  contentType: "text/html; charset=utf-8",
  title: "Team - " + mainData.eventInfo.name + " | " + mainData.communityName,
  description: mainData.eventInfo.description.short,
  keywords: mainData.seo.keywords,
  ogLocale:'en_US',
  author: "OSS Labs",
  creator: "OSS Labs",
  viewport: "width=device-width, initial-scale=1.0",
  ogTitle: "Team - " + mainData.eventInfo.name + " | " + mainData.communityName,
  ogDescription: mainData.eventInfo.description.short,
  ogImage: `${mainData.seo.hostUrl}/thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  ogUrl: mainData.seo.hostUrl,
  ogType: "website",
  twitterTitle: "Team - " + mainData.eventInfo.name + " | " + mainData.communityName,
  twitterDescription: mainData.eventInfo.description.short,
  twitterImage: `${mainData.seo.hostUrl}thumbnail.png?auto=format&fit=crop&frame=1&h=512&w=1024`,
  twitterCard: "summary_large_image",
});
</script>

<style scoped>
</style>
