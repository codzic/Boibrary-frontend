<svelte:head>
	<title>Boibrary</title>
</svelte:head>
<script>
	let bookCount = $state(500);
</script>

<section class="hero">
	<div class="container">
		<div class="logo">
			<img
				src="https://i.imgur.com/WDAoL9W.jpeg"
				alt="Boibrary Logo"
			/>
		</div>
		<h1>Boibrary</h1>
		<p class="tagline">
			Read More, Spend Less - Affordable Book Rentals Delivered to Your Door in Dhaka
		</p>
		<a href="#pricing" class="cta-button">Choose Your Plan</a>
	</div>
</section>

<section class="features">
	<div class="container">
		<h2>Why Choose Boibrary?</h2>
		<div class="feature-grid">
			<div class="feature-card">
				<div class="feature-icon">💰</div>
				<h3>Super Affordable</h3>
				<p>Read 4-6 books for the price of buying just one. Starting at only 360 tk/month!</p>
			</div>
			<div class="feature-card">
				<div class="feature-icon">🚚</div>
				<h3>Doorstep Delivery</h3>
				<p>Books delivered and picked up from your home. No need to visit any library.</p>
			</div>
			<div class="feature-card">
				<div class="feature-icon">📖</div>
				<h3>Wide Selection</h3>
				<p>Access hundreds of popular books from partnered bookshops across Dhaka.</p>
			</div>
			<div class="feature-card">
				<div class="feature-icon">🔒</div>
				<h3>Fully Refundable</h3>
				<p>500 tk safety deposit - fully refundable when you're done with the service.</p>
			</div>
		</div>
	</div>
</section>

<section class="pricing" id="pricing">
	<div class="container">
		<h2>Simple, Transparent Pricing</h2>
		<div class="pricing-grid">
			<div class="pricing-card">
				<div class="plan-name">Starter</div>
				<div class="plan-price">360<span>/month</span></div>
				<div class="plan-books">4 books per month</div>
				<ul class="plan-features">
					<li>Free delivery & pickup</li>
					<li>1 week per book</li>
					<li>Free extensions available</li>
				</ul>
				<button class="select-plan">Get Started</button>
			</div>

			<div class="pricing-card featured">
				<div class="badge">Most Popular</div>
				<div class="plan-name">Reader</div>
				<div class="plan-price">550<span>/month</span></div>
				<div class="plan-books">6 books per month</div>
				<ul class="plan-features">
					<li>Free delivery & pickup</li>
					<li>1 week per book</li>
					<li>Free extensions available</li>
				</ul>
				<button class="select-plan">Get Started</button>
			</div>

			<div class="pricing-card">
				<div class="plan-name">Bookworm</div>
				<div class="plan-price">900<span>/month</span></div>
				<div class="plan-books">Unlimited books</div>
				<ul class="plan-features">
					<li>Free delivery & pickup</li>
					<li>1 week per book</li>
					<li>Free extensions available</li>
					<li>Best value for avid readers</li>
				</ul>
				<button class="select-plan">Get Started</button>
			</div>

			<div class="pricing-card featured">
				<div class="badge">Premium</div>
				<div class="plan-name">VIP Express</div>
				<div class="plan-price">1200<span>/month</span></div>
				<div class="plan-books">Unlimited books</div>
				<ul class="plan-features">
					<li>⚡ 24-hour urgent delivery</li>
					<li>Free delivery & pickup</li>
					<li>1 week per book</li>
					<li>Free extensions available</li>
					<li>Priority support</li>
				</ul>
				<button class="select-plan">Get Started</button>
			</div>
		</div>

		<div class="special-offer">
			<div class="offer-badge">💎 Special Offer</div>
			<h2>Offline Membership</h2>
			<p class="offer-description">
				Visit our physical library location and enjoy unlimited reading at an unbeatable price!
			</p>

			<div class="offer-details">
				<div class="offer-price">
					<span class="price-amount">50 tk</span>
					<span class="price-period">/month</span>
				</div>
				<div class="offer-deposit">+ 500 tk one-time safety deposit (fully refundable)</div>
			</div>

			<ul class="offer-features">
				<li>✓ Unlimited books at our physical location</li>
				<li>✓ No delivery charges (visit & collect)</li>
				<li>✓ Same rental terms (1 week + free extensions)</li>
				<li>✓ Best value for frequent readers</li>
			</ul>

			<button class="select-plan">Get Offline Membership</button>
		</div>

		<div class="deposit-note">
			<h3>📝 One-Time Safety Deposit: 500 tk</h3>
			<p>
				Pay once for online plans, fully refundable when you deactivate your account. This protects
				both you and us, ensuring books are treated with care.
			</p>
		</div>
	</div>
</section>

<section class="how-it-works">
	<div class="container">
		<h2>How It Works</h2>
		<div class="steps">
			<div class="step">
				<div class="step-number">1</div>
				<h3>Choose a Plan</h3>
				<p>Select the perfect plan for your reading habits</p>
			</div>
			<div class="step">
				<div class="step-number">2</div>
				<h3>Order Books</h3>
				<p>Browse and order your favorite books online</p>
			</div>
			<div class="step">
				<div class="step-number">3</div>
				<h3>Get Delivery</h3>
				<p>Books arrive at your doorstep in 2 days</p>
			</div>
			<div class="step">
				<div class="step-number">4</div>
				<h3>Read & Enjoy</h3>
				<p>Take your time reading, extend if needed</p>
			</div>
			<div class="step">
				<div class="step-number">5</div>
				<h3>Return & Repeat</h3>
				<p>Return via courier and order your next book!</p>
			</div>
		</div>
	</div>
</section>

<footer>
	<div class="container">
		<p>&copy; 2025 Boibrary. Making reading accessible and affordable in Dhaka.</p>
		<p>📍 Currently serving Dhaka | 📧 Contact: hello@boibrary.com</p>
	</div>
</footer>

<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
	}

	.hero {
		background: linear-gradient(135deg, #ff8c42 0%, #ff6b35 100%);
		color: white;
		padding: 80px 20px;
		text-align: center;
		position: relative;
		overflow: hidden;
	}

	.hero::before {
		content: '';
		position: absolute;
		top: -50%;
		right: -10%;
		width: 500px;
		height: 500px;
		background: rgba(255, 255, 255, 0.1);
		border-radius: 50%;
		animation: float 6s ease-in-out infinite;
	}

	@keyframes float {
		0%,
		100% {
			transform: translateY(0px);
		}
		50% {
			transform: translateY(-20px);
		}
	}

	.container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 0 20px;
		position: relative;
		z-index: 1;
	}

	.logo {
		width: 100px;
		height: 100px;
		margin: 0 auto 20px;
	}

	.logo img {
		width: 100%;
		height: 100%;
		object-fit: contain;
    border-radius: 50%;
	}

	h1 {
		font-size: 3em;
		margin-bottom: 20px;
		font-weight: 700;
	}

	.tagline {
		font-size: 1.3em;
		margin-bottom: 30px;
		opacity: 0.95;
	}

	.cta-button {
		background: white;
		color: #ff6b35;
		padding: 15px 40px;
		font-size: 1.1em;
		border: none;
		border-radius: 50px;
		cursor: pointer;
		font-weight: 600;
		transition:
			transform 0.3s,
			box-shadow 0.3s;
		display: inline-block;
		text-decoration: none;
	}

	.cta-button:hover {
		transform: translateY(-2px);
		box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
	}

	.features {
		padding: 80px 20px;
		background: #f9f9f9;
	}

	.features h2 {
		text-align: center;
		font-size: 2.5em;
		margin-bottom: 50px;
		color: #ff6b35;
	}

	.feature-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		gap: 40px;
	}

	.feature-card {
		background: white;
		padding: 30px;
		border-radius: 15px;
		text-align: center;
		box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
		transition: transform 0.3s;
	}

	.feature-card:hover {
		transform: translateY(-5px);
	}

	.feature-icon {
		font-size: 3em;
		margin-bottom: 15px;
	}

	.feature-card h3 {
		color: #ff6b35;
		margin-bottom: 10px;
	}

	.pricing {
		padding: 80px 20px;
		background: white;
	}

	.pricing h2 {
		text-align: center;
		font-size: 2.5em;
		margin-bottom: 50px;
		color: #ff6b35;
	}

	.pricing-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		gap: 30px;
		max-width: 1200px;
		margin: 0 auto;
	}

	.pricing-card {
		background: linear-gradient(135deg, #fff 0%, #f9f9f9 100%);
		padding: 40px 30px;
		border-radius: 20px;
		text-align: center;
		border: 3px solid #e0e0e0;
		transition: all 0.3s;
		position: relative;
	}

	.pricing-card:hover {
		border-color: #ff6b35;
		transform: scale(1.05);
		box-shadow: 0 15px 35px rgba(255, 107, 53, 0.2);
	}

	.pricing-card.featured {
		border-color: #ff6b35;
		background: linear-gradient(135deg, #fff5f2 0%, #ffe8e0 100%);
	}

	.pricing-card.featured .badge {
		position: absolute;
		top: -15px;
		right: 20px;
		background: #ff6b35;
		color: white;
		padding: 5px 15px;
		border-radius: 20px;
		font-size: 0.85em;
		font-weight: 600;
	}

	.plan-name {
		font-size: 1.5em;
		color: #333;
		margin-bottom: 15px;
		font-weight: 600;
	}

	.plan-price {
		font-size: 3em;
		color: #ff6b35;
		font-weight: 700;
		margin-bottom: 10px;
	}

	.plan-price span {
		font-size: 0.4em;
		color: #666;
	}

	.plan-books {
		font-size: 1.2em;
		color: #666;
		margin-bottom: 25px;
	}

	.plan-features {
		list-style: none;
		margin-bottom: 30px;
	}

	.plan-features li {
		padding: 10px 0;
		border-bottom: 1px solid #e0e0e0;
	}

	.plan-features li:last-child {
		border-bottom: none;
	}

	.select-plan {
		background: #ff6b35;
		color: white;
		padding: 12px 30px;
		border: none;
		border-radius: 50px;
		cursor: pointer;
		font-weight: 600;
		transition: background 0.3s;
		width: 100%;
	}

	.select-plan:hover {
		background: #ff8c42;
	}

	.how-it-works {
		padding: 80px 20px;
		background: linear-gradient(135deg, #ff6b35 0%, #ff8c42 100%);
		color: white;
	}

	.how-it-works h2 {
		text-align: center;
		font-size: 2.5em;
		margin-bottom: 50px;
	}

	.steps {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
		gap: 30px;
		max-width: 1000px;
		margin: 0 auto;
	}

	.step {
		text-align: center;
	}

	.step-number {
		width: 60px;
		height: 60px;
		background: white;
		color: #ff6b35;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 1.8em;
		font-weight: 700;
		margin: 0 auto 20px;
	}

	.step h3 {
		margin-bottom: 10px;
		font-size: 1.3em;
	}

	footer {
		background: #333;
		color: white;
		text-align: center;
		padding: 30px 20px;
	}

	footer p {
		margin-bottom: 10px;
	}

	.deposit-note {
		background: #fff5f2;
		padding: 30px;
		border-radius: 15px;
		margin: 50px auto 0;
		max-width: 800px;
		border-left: 5px solid #ff6b35;
	}

	.deposit-note h3 {
		color: #ff6b35;
		margin-bottom: 10px;
	}

	.special-offer {
		grid-column: 1 / -1;
		background: linear-gradient(135deg, #fff9e6 0%, #ffe8b3 100%);
		border-radius: 20px;
		padding: 40px;
		text-align: center;
		border: 3px solid #fbbf24;
		position: relative;
		margin-top: 30px;
	}

	.offer-badge {
		position: absolute;
		top: -15px;
		left: 50%;
		transform: translateX(-50%);
		background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
		color: #78350f;
		padding: 8px 24px;
		border-radius: 25px;
		font-weight: 700;
		font-size: 1.1em;
		box-shadow: 0 4px 12px rgba(251, 191, 36, 0.4);
	}

	.special-offer h2 {
		font-size: 2.5em;
		color: #78350f;
		margin-bottom: 15px;
		margin-top: 10px;
	}

	.offer-description {
		font-size: 1.2em;
		color: #92400e;
		margin-bottom: 25px;
		max-width: 600px;
		margin-left: auto;
		margin-right: auto;
	}

	.offer-details {
		background: white;
		border-radius: 15px;
		padding: 25px;
		margin-bottom: 25px;
		display: inline-block;
	}

	.offer-price {
		margin-bottom: 10px;
	}

	.price-amount {
		font-size: 3.5em;
		font-weight: 700;
		color: #f59e0b;
	}

	.price-period {
		font-size: 1.2em;
		color: #92400e;
	}

	.offer-deposit {
		color: #92400e;
		font-size: 1.1em;
	}

	.offer-features {
		list-style: none;
		text-align: left;
		max-width: 500px;
		margin: 0 auto 30px;
		background: white;
		padding: 20px 30px;
		border-radius: 12px;
	}

	.offer-features li {
		padding: 12px 0;
		font-size: 1.1em;
		color: #78350f;
		border-bottom: 1px solid #fef3c7;
	}

	.offer-features li:last-child {
		border-bottom: none;
	}

	.special-offer .select-plan {
		background: linear-gradient(135deg, #fbbf24 0%, #f59e0b 100%);
		color: #78350f;
		font-size: 1.2em;
		padding: 15px 40px;
	}

	.special-offer .select-plan:hover {
		background: linear-gradient(135deg, #f59e0b 0%, #d97706 100%);
		transform: scale(1.05);
	}

	@media (max-width: 768px) {
		h1 {
			font-size: 2em;
		}

		.tagline {
			font-size: 1.1em;
		}

		.plan-price {
			font-size: 2.5em;
		}
	}
</style>
