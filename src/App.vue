<template>
  <div class="px-20 bg-blue-200">
    <div class="grid grid-cols-2 md:grid-cols-5 xl:grid-cols-10 p-5 gap-4 justify-items-center">
      <CategoryComponent
      v-for="category in categories"
      :key="category.id"
      :title="category.title"
      :image="category.image"
      :itemCount="category.itemCount"
      :bgColor="category.bgColor"
    />
    </div>
    <PromotionComponent />
  </div>
</template>
<script lang="ts">
import CategoryComponent from './components/CategoryComponent.vue'
import PromotionComponent from './components/PromotionComponent.vue'
export default {
  components: {
    CategoryComponent,
    PromotionComponent,
  },
  data() {
    return {
      categories: [
        {
          id: 1,
          title: 'Hamberger',
          itemCount: 14,
          image: '/cat-13 1.png',
          bgColor: '#F2FCE4',
        },
        {
          id: 2,
          title: 'Peach',
          itemCount: 17,
          image: '/cat-11 1.png',
          bgColor: '#FFFCEB',
        },
        {
          id: 3,
          title: 'Organic Kiwi',
          itemCount: 21,
          image: '/cat-12 1.png',
          bgColor: '#ECFFEC',
        },
        {
          id: 4,
          title: 'Red Apple',
          itemCount: 68,
          image: '/cat-9 1.png',
          bgColor: '#FEEFEA',
        },
        {
          id: 5,
          title: 'Snack',
          itemCount: 34,
          image: '/cat-3 1.png',
          bgColor: '#FFF3EB',
        },
        {
          id: 6,
          title: 'Black plum',
          itemCount: 25,
          image: '/cat-4 1.png',
          bgColor: '#FFF3FF',
        },
        {
          id: 7,
          title: 'Vegetable',
          itemCount: 65,
          image: '/cat-1 4.png',
          bgColor: '#F2FCE4',
        },
        {
          id: 8,
          title: 'Headphone',
          itemCount: 33,
          image: '/cat-15 1.png',
          bgColor: '#FFFCEB',
        },
        {
          id: 9,
          title: 'Cake & Milk',
          itemCount: 54,
          image: '/cat-14 1.png',
          bgColor: '#F2FCE4',
        },
        {
          id: 10,
          title: 'Orange',
          itemCount: 63,
          image: '/cat-7 1.png',
          bgColor: '#FFF3FF',
        },
      ],
    }
  },
}
</script>
