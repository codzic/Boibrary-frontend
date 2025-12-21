<svelte:head>
  <title>Books - Boibrary</title>
</svelte:head>

<script>
  let books = $state([
    { id: 1, title: 'The Alchemist', author: 'Paulo Coelho', price: 350 },
    { id: 2, title: 'Educated', author: 'Tara Westover', price: 420 },
    { id: 3, title: 'Atomic Habits', author: 'James Clear', price: 380 },
    { id: 4, title: 'Sapiens', author: 'Yuval Noah Harari', price: 450 },
    { id: 5, title: 'The Psychology of Money', author: 'Morgan Housel', price: 340 },
    { id: 6, title: '1984', author: 'George Orwell', price: 280 },
  ]);
</script>

<div class="books-page">
  <div class="container py-12">
    <h1 class="page-title">Available Books</h1>

    <div class="books-grid">
      {#each books as book}
        <div class="book-card">
          <div class="book-image">📖</div>
          <h3 class="book-title">{book.title}</h3>
          <p class="book-author">by {book.author}</p>
          <p class="book-price">{book.price} tk</p>
          
          <button class="btn btn-primary btn-block">
            Rent Now
          </button>
        </div>
      {/each}
    </div>
  </div>
</div>

<style>
  .books-page {
    min-height: 100vh;
    background: var(--gray-50);
  }

  .page-title {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--gray-800);
    margin-bottom: 32px;
  }

  .books-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 24px;
  }

  .book-card {
    background: white;
    border-radius: 12px;
    padding: 24px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s, box-shadow 0.3s;
    text-align: center;
  }

  .book-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15);
  }

  .book-image {
    font-size: 4rem;
    margin-bottom: 16px;
  }

  .book-title {
    font-size: 1.25rem;
    font-weight: 600;
    color: var(--gray-800);
    margin-bottom: 8px;
  }

  .book-author {
    color: var(--gray-600);
    margin-bottom: 16px;
  }

  .book-price {
    font-size: 1.5rem;
    font-weight: 700;
    color: var(--orange-primary);
    margin-bottom: 16px;
  }

  .btn-block {
    width: 100%;
  }
</style>