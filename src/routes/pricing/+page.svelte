<svelte:head>
	<title>Pricing - Boibrary</title>
</svelte:head>

<script>
  let plans = $state([
    {
      name: 'Starter',
      price: 360,
      books: '4 books per month',
      features: ['Free delivery & pickup', '1 week per book', 'Free extensions'],
      popular: false,
      premium: false
    },
    {
      name: 'Reader',
      price: 550,
      books: '6 books per month',
      features: ['Free delivery & pickup', '1 week per book', 'Free extensions'],
      popular: true,
      premium: false
    },
    {
      name: 'Bookworm',
      price: 900,
      books: 'Unlimited books',
      features: ['Free delivery & pickup', '1 week per book', 'Free extensions', 'Best value'],
      popular: false,
      premium: false
    },
    {
      name: 'VIP Express',
      price: 1200,
      books: 'Unlimited books',
      features: ['⚡ 24-hour delivery', 'Free delivery & pickup', '1 week per book', 'Priority support'],
      popular: false,
      premium: true
    }
  ]);
</script>

<div class="pricing-page">
  <div class="container py-12">
    <h1 class="page-title text-center">Choose Your Plan</h1>
    <p class="page-subtitle text-center">Start reading more for less</p>

    <div class="pricing-grid">
      {#each plans as plan}
        <div class="pricing-card" class:popular={plan.popular} class:premium={plan.premium}>
          {#if plan.popular}
            <span class="badge badge-popular">Most Popular</span>
          {/if}
          {#if plan.premium}
            <span class="badge badge-premium">Premium</span>
          {/if}

          <h3 class="plan-name">{plan.name}</h3>
          <div class="plan-price">
            {plan.price}
            <span class="price-period">/month</span>
          </div>
          <p class="plan-books">{plan.books}</p>

          <ul class="plan-features">
            {#each plan.features as feature}
              <li>
                <span class="check">✓</span>
                {feature}
              </li>
            {/each}
          </ul>

          <button class="btn btn-primary btn-block">
            Select Plan
          </button>
        </div>
      {/each}
    </div>

    <div class="deposit-notice">
      <h3>📝 One-Time Safety Deposit: 500 tk</h3>
      <p>
        Pay once, fully refundable when you deactivate your account. This protects both you and us, ensuring books are treated with care.
      </p>
    </div>
  </div>
</div>

<style>
  .pricing-page {
    min-height: 100vh;
    background: var(--gray-50);
  }

  .page-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--gray-800);
    margin-bottom: 16px;
  }

  .page-subtitle {
    color: var(--gray-600);
    font-size: 1.125rem;
    margin-bottom: 48px;
  }

  .pricing-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
    gap: 24px;
    max-width: 1200px;
    margin: 0 auto 48px;
  }

  .pricing-card {
    background: white;
    border-radius: 16px;
    padding: 32px 24px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    transition: all 0.3s;
    position: relative;
    border: 2px solid transparent;
  }

  .pricing-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
  }

  .pricing-card.popular {
    border-color: var(--orange-primary);
    background: linear-gradient(135deg, #fff5f2 0%, #ffe8e0 100%);
  }

  .pricing-card.premium {
    border-color: #fbbf24;
  }

  .badge {
    position: absolute;
    top: -12px;
    right: 20px;
    padding: 6px 16px;
    border-radius: 20px;
    font-size: 0.875rem;
    font-weight: 600;
  }

  .badge-popular {
    background: var(--orange-primary);
    color: white;
  }

  .badge-premium {
    background: #fbbf24;
    color: #78350f;
  }

  .plan-name {
    font-size: 1.5rem;
    font-weight: 600;
    color: var(--gray-800);
    margin-bottom: 16px;
  }

  .plan-price {
    font-size: 3rem;
    font-weight: 700;
    color: var(--orange-primary);
    margin-bottom: 8px;
  }

  .price-period {
    font-size: 1rem;
    color: var(--gray-600);
  }

  .plan-books {
    color: var(--gray-600);
    font-size: 1.125rem;
    margin-bottom: 24px;
  }

  .plan-features {
    list-style: none;
    margin-bottom: 24px;
    text-align: left;
  }

  .plan-features li {
    padding: 12px 0;
    border-bottom: 1px solid #e5e7eb;
  }

  .plan-features li:last-child {
    border-bottom: none;
  }

  .check {
    color: #10b981;
    margin-right: 8px;
    font-weight: 700;
  }

  .deposit-notice {
    max-width: 800px;
    margin: 48px auto 0;
    background: #fff5f2;
    border-left: 4px solid var(--orange-primary);
    padding: 24px;
    border-radius: 12px;
  }

  .deposit-notice h3 {
    color: var(--orange-primary);
    margin-bottom: 12px;
  }

  .deposit-notice p {
    color: var(--gray-700);
    line-height: 1.6;
  }

  .btn-block {
    width: 100%;
  }
</style>