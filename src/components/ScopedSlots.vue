<template lang="html">
  <div id="scoped-slots">
    <v-title text="Scoped Slots" />

    <div v-if="!showExample">
      What problem do they solve?
      <ul>
        <li>You need access to child data in the parent</li>
        <li>Something in the child might need to gracefully degrade</li>
        <li>
          You find yourself putting logic in the parent that should be in the
          child, because of certain restrictions around data
        </li>
        <li>You want customisability, but with defaults</li>
      </ul>
    </div>

    <div v-else id="examples">
      <v-button @click.native="simpleExample = !simpleExample">
        Show {{ simpleExample ? 'More Interesting' : 'Simple' }} Example
      </v-button>

      <div v-if="simpleExample" class="example">
        <v-card v-slot="slotProps">
          <div>I'm rendered from a <i>parent</i></div>
          <!-- slotProps is a safe default since there is only one slot prop in the child -->
          <div>{{slotProps.example}}</div>
        </v-card>

        <v-card >
          <!-- whoah new syntax -->
          <template #header>
            New Syntax, Destructured Props
          </template>

          <template v-slot:default="{ example }">
            <div>
              {{ example }}
            </div>
            <ul>
              <li>
                Slots using the <i>v-slot</i> directive can only use templates or components
              </li>
              <li>
                Any content <i>not</i> wrapped in a template is assumed to be the default
              </li>
              <li>
                In the other card, <i>v-slot</i> was used on the v-card component directly
                which is only acceptable if you're not accessing other slots/interacting with something
                other than defaults
              </li>
            </ul>
          </template>
        </v-card>

        <v-card>
          <template v-slot:[iAmDynamic]>
            I'm some dynamic slot content
          </template>
          <a @click="toggleDynamic">Toggle dynamic slot name</a>
        </v-card>
      </div>

      <div v-else class="example">
        <v-table
          :list="sailorSenshi"
          table-name="Sailor Scouts"
          v-slot="{ item }"
        >
          <td>{{ item.name }}</td>
          <td><img :src="item.img"/></td>
        </v-table>

        <v-table :list="groceryList" table-name="Groceries">
          <template v-slot:default="{item}">
            <td>{{ item.thing }}</td>
            <td>({{ item.amount}})</td>
          </template>
        </v-table>
      </div>
    </div>

    <v-button @click.native="toggleExample">Toggle Example</v-button>
  </div>
</template>

<script>
import VTitle from './common/VTitle'
import VButton from './common/VButton'
import VTable from './common/VTable'
import VCard from './common/VCard'
export default {
  name: 'scoped-slots',
  components: { VTitle, VButton, VTable, VCard },
  data () {
    return {
      showExample: false,
      simpleExample: true,
      iAmDynamic: 'header',
      sailorSenshi: [
        {
          name: 'Moon',
          img: 'http://www.sailorenergy.net/KawaiiGIFs/SMKSailorMoon.gif'
        },
        {
          name: 'Mercury',
          img:
            'http://www.sailorenergy.net/KawaiiGIFs/SMKSailorSuperMercury.gif'
        },
        {
          name: 'Jupiter',
          img: 'http://www.sailorenergy.net/KawaiiGIFs/SMKSailorJupiter.gif'
        },
        {
          name: 'Venus',
          img: 'http://www.sailorenergy.net/KawaiiGIFs/SMKSailorSuperVenus.gif'
        },
        {
          name: 'Mars',
          img: 'http://www.sailorenergy.net/KawaiiGIFs/SMKSailorSuperMars.gif'
        }
      ],

      groceryList: [
        { thing: 'Yogurt', amount: 1 },
        { thing: 'Apples', amount: 5 },
        { thing: 'Candy', amount: 100 },
        { thing: 'Garcinia Cambogia', amount: 2 }
      ]
    }
  },
  methods: {
    toggleExample () {
      this.showExample = !this.showExample
    },
    toggleDynamic () {
      if (this.iAmDynamic === 'header') {
        this.iAmDynamic = 'footer'
      } else {
        this.iAmDynamic = 'header'
      }
    }
  }
}
</script>

<style lang="css" scoped>
a {
  color: purple;
  font-weight: bold;
  cursor: pointer;
}

#examples {
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.example {
  display: flex;
  flex-direction: row;
}
</style>
