<template>
  <div>
    <title-bar :title-stack="titleStack" />
    <hero-bar>
      ประวัติการเข้าใช้
      <router-link slot="right" to="/" class="button">
        Dashboard
      </router-link>
    </hero-bar>
    <section class="section is-main-section">

      <card-component
        class="has-table has-mobile-sort-spaced"
        title="Clients"
        icon="account-multiple"
      >
        <clients-table-sample
          :data-url="`${$router.options.base}data-sources/clients.json`"
          :checkable="true"
        />
      </card-component>

      <hr />
      <hr />

    </section>
  </div>
</template>

<script>
import ClientsTableSample from '@/components/ClientsTableSample'
import CardComponent from '@/components/CardComponent'
import TitleBar from '@/components/TitleBar'
import HeroBar from '@/components/HeroBar'
export default {
  name: 'Tables',
  components: {
    HeroBar,
    TitleBar,
    CardComponent,
    ClientsTableSample
  },
  computed: {
    titleStack () {
      return ['Admin', 'ประวัติการเข้าใช้']
    }
  }
}
</script>
