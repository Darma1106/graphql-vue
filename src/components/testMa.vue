<template>
  <div>testma</div>
</template>

<script setup lang="ts">
import { useQuery } from '@vue/apollo-composable'
import gql from 'graphql-tag'
import { watch } from 'vue'

const { result, loading } = useQuery(gql`
  query getUsers {
    hero {
      name
      id
    }
  }
`)

watch(loading, (val) => {
  if (val === false) {
    console.log(result.value)
  }
})
</script>

<style lang="less" scoped></style>
