<template>
  <v-container grid-list-md>
    <v-layout
      text-xs-center
      wrap
    >
      <v-flex
        v-for="cat in cats"
        :key="cat.id"
        xs12
        sm6
        lg4
      >
        <v-card>
          <v-img
            class="white--text"
            height="300px"
            :src="`https://cataas.com/cat?height=300&color=${cat.color}`"
          />
          <v-card-title primary-title>
            <div>
              <h3 class="headline text-uppercase">
                {{ cat.name }}
              </h3>
              <div>
                {{ cat.description }}
              </div>
            </div>
          </v-card-title>
          <v-card-actions>
            <v-tooltip
              top
              class="flex"
            >
              <v-btn
                large
                slot="activator"
                color="green"
              >
                {{ cat.health }}
              </v-btn>
              <span>Health</span>
            </v-tooltip>
            <v-tooltip
              top
              class="flex"
            >
              <v-btn
                large
                slot="activator"
                color="blue"
              >
                {{ cat.strength }}
              </v-btn>
              <span>Strength</span>
            </v-tooltip>
            <v-tooltip
              top
              class="flex"
            >
              <v-btn
                large
                slot="activator"
                color="red"
              >
                {{ cat.claw_size }}
              </v-btn>
              <span>Claw size</span>
            </v-tooltip>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import gql from 'graphql-tag'
export default {
  name: 'KittyCards',
  data() {
    return {
      cats: {}
    }
  },
  apollo: {
    cats: {
      query: gql`
        {
          cats {
            id
            name
            description
            color
            health
            strength
            claw_size
          }
        }
      `,
      update(data) {
        return data.cats;
      },
      subscribeToMore: {
        document: gql`
          subscription catSub {
            cats {
              id
              name
              description
              color
              health
              strength
              claw_size
            }
          }
        `,
        updateQuery: (previousResult, { subscriptionData }) => {
          return subscriptionData.data;
        }
      }
    }
  }
}
</script>
