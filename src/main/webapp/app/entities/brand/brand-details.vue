<template>
  <div class="row justify-content-center">
    <div class="col-8">
      <div v-if="brand">
        <h2 class="jh-entity-heading" data-cy="brandDetailsHeading"><span>Brand</span> {{ brand.id }}</h2>
        <dl class="row jh-entity-details">
          <dt>
            <span>Name</span>
          </dt>
          <dd>
            <span>{{ brand.name }}</span>
          </dd>
        </dl>
        <button type="submit" @click.prevent="previousState()" class="btn btn-info" data-cy="entityDetailsBackButton">
          <font-awesome-icon icon="arrow-left"></font-awesome-icon>&nbsp;<span>Zurück</span>
        </button>
        <router-link v-if="brand.id" :to="{ name: 'BrandEdit', params: { brandId: brand.id } }" custom v-slot="{ navigate }">
          <button @click="navigate" class="btn btn-primary">
            <font-awesome-icon icon="pencil-alt"></font-awesome-icon>&nbsp;<span>Bearbeiten</span>
          </button>
        </router-link>
      </div>
    </div>
  </div>
</template>

<script lang="ts" src="./brand-details.component.ts"></script>
