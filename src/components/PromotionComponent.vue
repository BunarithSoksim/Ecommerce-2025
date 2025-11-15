// ...existing code...
<template>
  <div class="promo-card" role="region" aria-label="Promotion card">
    <div class="promo-media">
      <img :src="image" :alt="title" class="promo-img" />
      <span v-if="badgeText" class="badge">{{ badgeText }}</span>
    </div>

    <div class="promo-body">
      <h3 class="promo-title">{{ title }}</h3>
      <p class="promo-sub">{{ subtitle }}</p>

      <div class="promo-footer">
        <div class="promo-price">
          <span class="price">{{ formattedPrice }}</span>
          <span v-if="discount" class="discount">-{{ discount }}%</span>
        </div>

        <button class="cta" @click="$emit('cta-click')">
          {{ buttonText }}
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PromotionComponent',
  props: {
    image: {
      type: String,
      default: '/images/default-product.jpg',
    },
    title: {
      type: String,
      default: 'Every Fresh & Clean with Our Products',
    },
    subtitle: {
      type: String,
      default: 'Natural ingredients, long-lasting freshness.',
    },
    price: {
      type: Number,
      default: 9.99,
    },
    discount: {
      type: [Number, String],
      default: null,
    },
    badgeText: {
      type: String,
      default: 'New',
    },
    buttonText: {
      type: String,
      default: 'Shop Now',
    },
    currency: {
      type: String,
      default: '$',
    },
  },
  computed: {
    formattedPrice() {
      return `${this.currency}${Number(this.price).toFixed(2)}`
    },
  },
}
</script>

<style scoped>
.promo-card {
  display: flex;
  gap: 1rem;
  align-items: center;
  background: #ffffff;
  border-radius: 12px;
  box-shadow: 0 6px 18px rgba(16, 24, 40, 0.06);
  padding: 1rem;
  max-width: 720px;
}

.promo-media {
  position: relative;
  width: 160px;
  flex: 0 0 160px;
}

.promo-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 8px;
  display: block;
}

.badge {
  position: absolute;
  left: 8px;
  top: 8px;
  background: #ef4444;
  color: #fff;
  font-weight: 700;
  padding: 4px 8px;
  border-radius: 999px;
  font-size: 0.75rem;
  line-height: 1;
}

.promo-body {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.promo-title {
  margin: 0;
  font-size: 1.25rem;
  font-weight: 700;
  color: #0f172a;
}

.promo-sub {
  margin: 0;
  color: #475569;
  font-size: 0.95rem;
}

.promo-footer {
  display: flex;
  gap: 1rem;
  align-items: center;
  margin-top: 0.5rem;
}

.promo-price {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.price {
  font-size: 1.1rem;
  font-weight: 700;
  color: #0f172a;
}

.discount {
  background: #ecfdf5;
  color: #065f46;
  padding: 2px 6px;
  border-radius: 6px;
  font-weight: 700;
  font-size: 0.85rem;
}

.cta {
  background: #2563eb;
  color: #fff;
  border: none;
  padding: 0.5rem 0.9rem;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 700;
  transition: background 0.12s ease;
}

.cta:hover {
  background: #1e40af;
}

/* Responsive */
@media (max-width: 640px) {
  .promo-card {
    flex-direction: column;
    align-items: stretch;
  }
  .promo-media {
    width: 100%;
    flex: none;
  }
  .promo-img {
    height: 180px;
  }
  .promo-footer {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>
// ...existing code...
