# Kittymon, Demo App To Illustrate Making A Simple Real-time Vue.js App With Hasura

This app is meant to be a companion to the talk I made on February 21st 2019, titled "Vue.js Real-time Apps With Hasura".

You can follow [the steps in the slides](https://github.com/VuejsVienna/VuejsVienna/tree/master/talks/2019/february/vue-js-with-hasura) to set up this demo project from scratch with Hasura, or...

1. Clone this repo

1. Set up a Hasura instance on Heroku (again, [steps available in talk slides](https://github.com/VuejsVienna/VuejsVienna/tree/master/talks/2019/february/vue-js-with-hasura))

1. In src/vue-apollo.js, change httpEndpoint and wsEndpoint to match your Hasura instance

```
const httpEndpoint = 'https://appname.herokuapp.com/v1alpha1/graphql'
const wsEndpoint = 'ws://appname.herokuapp.com/v1alpha1/graphql'
```

