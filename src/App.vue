<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated>
      <q-toolbar class="custom-toolbar">

        <q-toolbar-title class="nav-title">
          <router-link to="/" style="color: #6d3939;">
            UAS Praktikum
          </router-link>
        </q-toolbar-title>

        <q-btn-dropdown class="custom-dropdown" label="Daftar Tugas" dropdown-icon="^">
          <q-list class="nav-list">
            <q-item clickable v-close-popup>
              <router-link to="/">
                <q-item-section>
                  <q-item-label style="color: #6d3939;">Weather</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas1">
                <q-item-section>
                  <q-item-label style="color: #6d3939;">Tugas 1</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas2">
                <q-item-section>
                  <q-item-label style="color: #6d3939;">Tugas 2</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas3">
                <q-item-section>
                  <q-item-label style="color: #6d3939;">Tugas 3</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas4">
                <q-item-section>
                  <q-item-label style="color: #6d3939;">Tugas 4</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas5">
                <q-item-section>
                  <q-item-label style="color: #6d3939;">Tugas 5</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas6">
                <q-item-section>
                  <q-item-label style="color: #6d3939;">Tugas 6</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
            <q-item clickable v-close-popup>
              <router-link to="/tugas7">
                <q-item-section>
                  <q-item-label style="color: #6d3939;">Tugas 7</q-item-label>
                </q-item-section>
              </router-link>
            </q-item>
          </q-list>
        </q-btn-dropdown>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view></router-view>
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  setup() {

  },
};
</script>

<style>
@import './assets/index.css';

.custom-toolbar {
  background-color: var(--brown);
  color: var(--light-pink);
}

.custom-dropdown {
  background-color: var(--dark-burgundy);
  color: var(--lightest-pink);
}

.nav-list {
  background-color: var(--brown);
  color: var(--lightest-pink);
}

.nav-list .q-item link {
  text-decoration: none;
}

</style>
