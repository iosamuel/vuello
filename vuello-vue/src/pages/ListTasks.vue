<template>
  <div></div>
</template>

<script setup>
import gql from "graphql-tag";
import { useApolloClient } from "../composables/useApolloClient.js";

const apollo = useApolloClient();

apollo.client
  .query({
    query: gql`
      query MyQuery {
        tasks {
          id
          status
          text
          user_id
        }
      }
    `,
  })
  .then((res) => console.log(res));
</script>

<style>
</style>
