<script>
import CustomTree from './CustomTree.vue';

export default {
  name: 'SecondPart',
  components: {CustomTree },
  data() {
    return {
      nestedObject: {
        address: {
        street: "Downing St.",
        details: {
          apartment: 'C',
          floor: 2,
          code: '2938B'
        },
        country: 'UK'
        },
        miscInfo: {
        socialMedia: {
          facebook: {
          history: {
            allHistory: {
              2020: {
                events: '0 events :('
              },
              2019: {
                allMyData: 'isnt safe',
                events: '12 events'
              },
              2018: {
                allMyData: 'Never Forget',
                events: '234 events'
              }
            }
          }

          },
          twitter: {
          feed: '1234 tweets',
          likes: '1234 likes',
          pinnedTweet: {
              'hashtag': '#someHashTag',
              handle: '@itsamemario',
              text: 'Very funny joke'
          }
          },
          name: 'pseudo2000'
        }
        },
        firstName: 'Hello',
        lastName: 'World'
      }
      // If the object changes, your code should work
      // nestedObject: {
      //   somethingElse: {
      //     key2: {
      //       nested: {
      //         more: "nesting"
      //       }
      //     },
      //     hop: "hophop"
      //   },
      //   yipeee: "yeah"
      // }
    }
  },
  methods:{
    displayDetails(el) {
      alert(el)
    }
  }
}
</script>
<template>
    <div>
        <textarea >{{ nestedObject }}</textarea>
        <CustomTree v-bind:nestedObject="nestedObject" />
    </div>
</template> 

<style lang="css">
textarea {
  width: 100%;
  min-height: 200px;
}
</style>

  