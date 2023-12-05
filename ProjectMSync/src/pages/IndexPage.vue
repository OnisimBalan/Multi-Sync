<template>
  <q-page class="row justify-evenly" style="padding: 5px">
    <q-tabs v-model="tab" vertical>
      <div style="margin-left: 15px; margin-top: 15px">
        <q-select
          filled
          v-model="model"
          label="Search"
          color="primary"
          :options="search"
          style="width: 500px"
          behavior="menu"
          outlined
        />
      </div>

      <main-project></main-project>
    </q-tabs>
  </q-page>
</template>

<script lang="ts">
import { Todo, Meta } from 'components/models';
import MainProject from 'components/MainProject.vue';
import { defineComponent, ref } from 'vue';

const filters = ['Footbal', 'Date', 'School', 'Shopping', 'Fitness'];
const search = [
  'Footbal team timisoara',
  'Date online',
  'School books',
  'Shopping in town',
  'Fitness gym',
];

export default defineComponent({
  name: 'IndexPage',
  components: { MainProject },
  setup() {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'ct1',
      },
      {
        id: 2,
        content: 'ct2',
      },
      {
        id: 3,
        content: 'ct3',
      },
      {
        id: 4,
        content: 'ct4',
      },
      {
        id: 5,
        content: 'ct5',
      },
    ]);
    const meta = ref<Meta>({
      totalCount: 1200,
    });
    return {
      todos,
      meta,
      model: ref(null),
      modelMultiple: ref(null),
      search,
      tab: ref('mails'),
      filters,
    };
  },
});
</script>
