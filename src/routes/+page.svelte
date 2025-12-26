<script>
	import './page.css';
	import { onMount } from 'svelte';
	import Slide1 from '$lib/components/carousels/Slide1/Slide1.svelte';
	import Slide2 from '$lib/components/carousels/Slide2/Slide2.svelte';
	import Slide3 from '$lib/components/carousels/Slide3/Slide3.svelte';
	import { slide, fly } from 'svelte/transition';

	let currentSlide = $state(0);
	let isAutoPlaying = $state(true);
	let autoPlayInterval;

	const slides = [Slide1, Slide2, Slide3];
	const slideInterval = 4000;

	// One time flow
	let hasCompleted = $state(false);

	function nextSlide() {
		if (currentSlide + 1 < slides.length) {
			currentSlide++;
		} else {
			hasCompleted = true;
		}
	}

	onMount(() => {
		const interval = setInterval(() => {
			if (!hasCompleted) {
				nextSlide();
			} else {
				clearInterval(interval);
			}
		}, slideInterval);

		return () => clearInterval(interval);
	});
</script>

<svelte:head>
	<title>Boibrary</title>
</svelte:head>

<section class="hero">
	<!-- svelte-ignore svelte_component_deprecated -->
	<svelte:component this={slides[currentSlide]} />
</section>





    <!-- <section class="hero">
        <div class="container">
            <div class="logo">
                <img src="https://i.imgur.com/your-logo-here.png" alt="Boibrary Logo" onerror="this.parentElement.innerHTML='📚'">
            </div>
            <h1>Boibrary</h1>
            <p class="tagline">Read More, Spend Less - Affordable Book Rentals Delivered to Your Door in Dhaka</p>
            <a href="#pricing" class="cta-button">Choose Your Plan</a>
        </div>
    </section> -->

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
                <p class="offer-description">Visit our physical library location and enjoy unlimited reading at an unbeatable price!</p>
                
                <div class="offer-details">
                    <div class="offer-price">
                        <span class="price-amount">50 tk</span>
                        <span class="price-period">/month</span>
                    </div>
                    <div class="offer-deposit">
                        + 500 tk one-time safety deposit (fully refundable)
                    </div>
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
                <p>Pay once for online plans, fully refundable when you deactivate your account. This protects both you and us, ensuring books are treated with care.</p>
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
            <p>&copy; 2025 Boibrary. All Rights Reserved.</p>
            <p>📍 Currently serving Mirpur-2 | 📧 Contact: hello@boibrary.com</p>
        </div>
    </footer>