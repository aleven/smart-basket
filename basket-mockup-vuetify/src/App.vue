<template>
  <v-app>
    <v-navigation-drawer
      fixed
      :mini-variant="miniVariant"
      :clipped="clipped"
      v-model="drawer"
      app
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"></v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"></v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar color="primary" fixed app :clipped-left="clipped">
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <!-- <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon v-html="miniVariant ? 'chevron_right' : 'chevron_left'"></v-icon>
      </v-btn>
      <v-btn icon @click.stop="clipped = !clipped">
        <v-icon>web</v-icon>
      </v-btn>
      <v-btn icon @click.stop="fixed = !fixed">
        <v-icon>remove</v-icon>
      </v-btn> -->
      <v-toolbar-title v-text="title"></v-toolbar-title>
      <!-- <v-spacer></v-spacer> -->
      <!-- <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>menu</v-icon>
      </v-btn> -->
    </v-toolbar>

    <v-content>
      <v-container fluid>
        <!--
        <v-slide-y-transition mode="out-in">
          <v-layout column align-center>
            <img src="/public/v.png" alt="Vuetify.js" class="mb-5" />
            <blockquote>
              &#8220;First, solve the problem. Then, write the code.&#8221;
              <footer>
                <small>
                  <em>&mdash;John Johnson</em>
                </small>
              </footer>
            </blockquote>
          </v-layout>
        </v-slide-y-transition>
        -->

        <v-form v-model="valid">
      <v-text-field
        label="Codice Paziente"
        v-model="pazoie"
        :rules="nameRules"
        required
      ></v-text-field>
    </v-form>

    <!-- <v-list>
      <v-list-tile
        value="true"
        v-for="num in 20"
        :key="num"
      >
        <v-list-tile-action>
          <v-icon>mdi-account-card-details</v-icon>
        </v-list-tile-action>
        <v-list-tile-content>
          <v-list-tile-title v-text="'Paziente' + num"></v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list> -->

    <v-list two-line>
      <template v-for="num in 20">
        <!-- <v-subheader v-if="item.header" v-text="num"></v-subheader> -->
        <!-- <v-divider v-else-if="item.divider" v-bind:inset="item.inset"></v-divider> -->
        <!-- <v-list-tile avatar v-else v-bind:key="num" @click=""> -->
        <v-list-tile avatar v-bind:key="num" @click="">
          <v-list-tile-avatar>
            <!-- <img v-bind:src="item.avatar"> -->
            <v-icon>mdi-account-card-details</v-icon>
          </v-list-tile-avatar>
          <v-list-tile-content>
            <v-list-tile-title v-text="'Paziente '+num"></v-list-tile-title>
            <v-list-tile-sub-title v-text="'codice'+ num"></v-list-tile-sub-title>
          </v-list-tile-content>
        </v-list-tile>
      </template>
    </v-list>

      </v-container>
    </v-content>

    <!-- <v-navigation-drawer
      temporary
      :right="right"
      v-model="rightDrawer"
      fixed
    >
      <v-list>
        <v-list-tile @click.native="right = !right">
          <v-list-tile-action>
            <v-icon>compare_arrows</v-icon>
          </v-list-tile-action>
          <v-list-tile-title>Switch drawer (click me)</v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer> -->

    <v-footer :fixed="fixed" app>
      <span>&copy; aleven.it 2017</span>
    </v-footer>
  </v-app>

</template>

<script>
  export default {
    data () {
      return {
        clipped: false,
        drawer: false,
        fixed: true,
        items: [
          { icon: 'bubble_chart', title: 'DEMO CESTINO' },
          { icon: 'bubble_chart', title: 'DEMO PORTAL' },
        ],
        miniVariant: false,
        // right: true,
        // rightDrawer: false,
        title: 'SALA OPERATORIA 1'
      }
    }
  }
</script>
