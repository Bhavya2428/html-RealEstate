# html-RealEstate

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>DreamNest Real Estate</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        /* ========== Global styles ========== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Helvetica, sans-serif;
        }

        body {
            background-color: #f5f5f5;
            color: #333;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        .container {
            width: 90%;
            max-width: 1100px;
            margin: 0 auto;
        }

        /* ========== Header & navigation ========== */
        header {
            background: #0b3954;
            color: #fff;
            padding: 15px 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 20px;
        }

        .nav-links li a {
            font-weight: 600;
        }

        .nav-links li a:hover {
            text-decoration: underline;
        }

        /* ========== Hero section ========== */
        .hero {
            background: linear-gradient(
                    rgba(0, 0, 0, 0.5),
                    rgba(0, 0, 0, 0.5)
                ),
                url("https://images.pexels.com/photos/106399/pexels-photo-106399.jpeg")
                center/cover no-repeat;
            color: #fff;
            padding: 80px 0;
            text-align: center;
        }

        .hero h1 {
            font-size: 40px;
            margin-bottom: 10px;
        }

        .hero p {
            font-size: 18px;
            margin-bottom: 20px;
        }

        .btn-primary {
            background: #ff7f50;
            border: none;
            padding: 10px 20px;
            color: #fff;
            font-size: 16px;
            border-radius: 4px;
            cursor: pointer;
        }

        .btn-primary:hover {
            background: #ff6a31;
        }

        /* ========== Filters section ========== */
        .filters-section {
            background: #fff;
            padding: 20px 0;
            box-shadow: 0 2px 4px rgba(0,0,0,0.06);
        }

        .filters-form {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            align-items: center;
            justify-content: space-between;
        }

        .filters-form label {
            font-size: 14px;
            margin-bottom: 4px;
            display: block;
        }

        .filter-group {
            flex: 1 1 150px;
            min-width: 150px;
        }

        .filters-form select,
        .filters-form input {
            width: 100%;
            padding: 8px;
            border-radius: 4px;
            border: 1px solid #ccc;
        }

        .filters-form button {
            margin-top: 18px;
        }

        /* ========== Property listings ========== */
        .listings {
            padding: 30px 0 40px;
        }

        .listings-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            margin-bottom: 15px;
        }

        .listings-header h2 {
            font-size: 24px;
        }

        .property-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .property-card {
            background: #fff;
            border-radius: 6px;
            overflow: hidden;
            box-shadow: 0 2px 6px rgba(0,0,0,0.08);
            display: flex;
            flex-direction: column;
        }

        .property-card img {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .property-body {
            padding: 15px;
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .property-title {
            font-size: 18px;
            font-weight: bold;
            margin-bottom: 6px;
        }

        .property-location {
            font-size: 14px;
            color: #777;
            margin-bottom: 8px;
        }

        .property-details {
            font-size: 14px;
            margin-bottom: 10px;
        }

        .property-price {
            font-size: 16px;
            font-weight: bold;
            color: #0b3954;
            margin-top: auto;
        }

        .property-type-badge {
            display: inline-block;
            background: #e1efff;
            color: #0b3954;
            font-size: 12px;
            padding: 3px 8px;
            border-radius: 20px;
            margin-bottom: 6px;
        }

        /* ========== Inquiry form ========== */
        .inquiry-section {
            background: #0b3954;
            color: #fff;
            padding: 40px 0;
        }

        .inquiry-layout {
            display: grid;
            grid-template-columns: 1.1fr 1fr;
            gap: 30px;
            align-items: flex-start;
        }

        .inquiry-section h2 {
            margin-bottom: 10px;
            font-size: 24px;
        }

        .inquiry-section p {
            margin-bottom: 20px;
        }

        .inquiry-form-group {
            margin-bottom: 15px;
        }

        .inquiry-form-group label {
            font-size: 14px;
            display: block;
            margin-bottom: 5px;
        }

        .inquiry-form-group input,
        .inquiry-form-group select,
        .inquiry-form-group textarea {
            width: 100%;
            padding: 8px;
            border-radius: 4px;
            border: 1px solid #ccc;
        }

        .inquiry-form-group textarea {
            resize: vertical;
            min-height: 80px;
        }

        .inquiry-note {
            font-size: 13px;
            margin-top: 10px;
            color: #d9e6ff;
        }

        .success-message {
            margin-top: 10px;
            font-size: 14px;
            color: #b4ffb4;
            display: none;
        }

        /* ========== Footer ========== */
        footer {
            background: #02111b;
            color: #bbb;
            text-align: center;
            padding: 12px 0;
            font-size: 13px;
        }

        /* ========== Responsive design ========== */
        @media (max-width: 900px) {
            .property-grid {
                grid-template-columns: repeat(2, 1fr);
            }

            .inquiry-layout {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 600px) {
            nav {
                flex-direction: column;
                gap: 10px;
            }

            .hero h1 {
                font-size: 30px;
            }

            .property-grid {
                grid-template-columns: 1fr;
            }

            .filters-form {
                flex-direction: column;
                align-items: stretch;
            }
        }
    </style>
</head>
<body>

    <!-- ========== Header ========== -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">DreamNest Real Estate</div>
                <ul class="nav-links">
                    <li><a href="#listings">Properties</a></li>
                    <li><a href="#inquiry">Inquiry</a></li>
                    <li><a href="#top">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- ========== Hero section ========== -->
    <section class="hero" id="top">
        <div class="container">
            <h1>Find Your Perfect Home</h1>
            <p>Explore verified properties with trusted agents and transparent pricing.</p>
            <button class="btn-primary" onclick="document.getElementById('inquiry').scrollIntoView({behavior: 'smooth'})">
                Get a Callback
            </button>
        </div>
    </section>

    <!-- ========== Filters section ========== -->
    <section class="filters-section">
        <div class="container">
            <form class="filters-form" id="filtersForm">
                <div class="filter-group">
                    <label for="locationFilter">Location</label>
                    <select id="locationFilter">
                        <option value="all">Any location</option>
                        <option value="delhi">Delhi</option>
                        <option value="mumbai">Mumbai</option>
                        <option value="pune">Pune</option>
                        <option value="bangalore">Bangalore</option>
                    </select>
                </div>

                <div class="filter-group">
                    <label for="typeFilter">Property Type</label>
                    <select id="typeFilter">
                        <option value="all">Any type</option>
                        <option value="apartment">Apartment</option>
                        <option value="villa">Villa</option>
                        <option value="plot">Plot</option>
                    </select>
                </div>

                <div class="filter-group">
                    <label for="minPrice">Min Price</label>
                    <input type="number" id="minPrice" placeholder="e.g. 2000000">
                </div>

                <div class="filter-group">
                    <label for="maxPrice">Max Price</label>
                    <input type="number" id="maxPrice" placeholder="e.g. 8000000">
                </div>

                <div class="filter-group" style="max-width: 150px;">
                    <button type="button" class="btn-primary" id="applyFiltersBtn">
                        Apply
                    </button>
                </div>
            </form>
        </div>
    </section>

    <!-- ========== Property listings ========== -->
    <section class="listings" id="listings">
        <div class="container">
            <div class="listings-header">
                <h2>Featured Properties</h2>
                <span id="resultsCount">6 results</span>
            </div>

            <div class="property-grid" id="propertyGrid">
                <!-- Property 1 -->
                <div class="property-card"
                     data-location="delhi"
                     data-type="apartment"
                     data-price="4500000">
                    <img src="https://images.pexels.com/photos/259597/pexels-photo-259597.jpeg"
                         alt="Modern apartment">
                    <div class="property-body">
                        <span class="property-type-badge">Apartment</span>
                        <div class="property-title">2 BHK Modern Apartment</div>
                        <div class="property-location">Dwarka, Delhi</div>
                        <div class="property-details">
                            2 Beds • 2 Baths • 980 sq ft
                        </div>
                        <div class="property-price">₹45,00,000</div>
                    </div>
                </div>

                <!-- Property 2 -->
                <div class="property-card"
                     data-location="mumbai"
                     data-type="apartment"
                     data-price="8500000">
                    <img src="https://images.pexels.com/photos/439391/pexels-photo-439391.jpeg"
                         alt="Luxury apartment">
                    <div class="property-body">
                        <span class="property-type-badge">Apartment</span>
                        <div class="property-title">3 BHK Sea View Apartment</div>
                        <div class="property-location">Bandra, Mumbai</div>
                        <div class="property-details">
                            3 Beds • 3 Baths • 1400 sq ft
                        </div>
                        <div class="property-price">₹85,00,000</div>
                    </div>
                </div>

                <!-- Property 3 -->
                <div class="property-card"
                     data-location="pune"
                     data-type="villa"
                     data-price="12000000">
                    <img src="https://images.pexels.com/photos/259580/pexels-photo-259580.jpeg"
                         alt="Villa">
                    <div class="property-body">
                        <span class="property-type-badge">Villa</span>
                        <div class="property-title">Luxury 4 BHK Villa</div>
                        <div class="property-location">Hinjewadi, Pune</div>
                        <div class="property-details">
                            4 Beds • 4 Baths • Private Garden
                        </div>
                        <div class="property-price">₹1,20,00,000</div>
                    </div>
                </div>

                <!-- Property 4 -->
                <div class="property-card"
                     data-location="bangalore"
                     data-type="apartment"
                     data-price="6000000">
                    <img src="https://images.pexels.com/photos/439391/pexels-photo-439391.jpeg"
                         alt="Apartment">
                    <div class="property-body">
                        <span class="property-type-badge">Apartment</span>
                        <div class="property-title">2 BHK IT Park Apartment</div>
                        <div class="property-location">Whitefield, Bangalore</div>
                        <div class="property-details">
                            2 Beds • 2 Baths • Club House
                        </div>
                        <div class="property-price">₹60,00,000</div>
                    </div>
                </div>

                <!-- Property 5 -->
                <div class="property-card"
                     data-location="mumbai"
                     data-type="plot"
                     data-price="3000000">
                    <img src="https://images.pexels.com/photos/1643383/pexels-photo-1643383.jpeg"
                         alt="Residential plot">
                    <div class="property-body">
                        <span class="property-type-badge">Plot</span>
                        <div class="property-title">Residential Plot 1200 sq ft</div>
                        <div class="property-location">Panvel, Mumbai</div>
                        <div class="property-details">
                            Clear Title • Gated Community
                        </div>
                        <div class="property-price">₹30,00,000</div>
                    </div>
                </div>

                <!-- Property 6 -->
                <div class="property-card"
                     data-location="delhi"
                     data-type="villa"
                     data-price="15000000">
                    <img src="https://images.pexels.com/photos/106399/pexels-photo-106399.jpeg"
                         alt="Premium villa">
                    <div class="property-body">
                        <span class="property-type-badge">Villa</span>
                        <div class="property-title">Premium 5 BHK Villa</div>
                        <div class="property-location">South Delhi</div>
                        <div class="property-details">
                            5 Beds • 5 Baths • Swimming Pool
                        </div>
                        <div class="property-price">₹1,50,00,000</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ========== Inquiry form section ========== -->
    <section class="inquiry-section" id="inquiry">
        <div class="container">
            <div class="inquiry-layout">
                <div>
                    <h2>Request a Call from Our Property Expert</h2>
                    <p>
                        Share your requirements and our team will get in touch
                        with you within 24 hours with the best options.
                    </p>

                    <form id="inquiryForm" novalidate>
                        <div class="inquiry-form-group">
                            <label for="name">Full Name *</label>
                            <input type="text" id="name" required placeholder="Enter your full name">
                        </div>

                        <div class="inquiry-form-group">
                            <label for="email">Email *</label>
                            <input type="email" id="email" required placeholder="yourname@example.com">
                        </div>

                        <div class="inquiry-form-group">
                            <label for="phone">Phone *</label>
                            <input type="tel" id="phone" required placeholder="10-digit mobile number">
                        </div>

                        <div class="inquiry-form-group">
                            <label for="budget">Approximate Budget</label>
                            <select id="budget">
                                <option value="">Select budget</option>
                                <option value="under-50">Below ₹50,00,000</option>
                                <option value="50-100">₹50,00,000 – ₹1,00,00,000</option>
                                <option value="above-100">Above ₹1,00,00,000</option>
                            </select>
                        </div>

                        <div class="inquiry-form-group">
                            <label for="message">Message / Requirements</label>
                            <textarea id="message" placeholder="Preferred location, BHK, amenities etc."></textarea>
                        </div>

                        <button type="submit" class="btn-primary">
                            Submit Inquiry
                        </button>

                        <div class="inquiry-note">
                            *By submitting, you agree to receive calls and emails
                            regarding property updates and offers.
                        </div>
                        <div class="success-message" id="successMessage">
                            Thank you! Your inquiry has been submitted. Our team will contact you shortly.
                        </div>
                    </form>
                </div>

                <div>
                    <h3>Why Choose DreamNest?</h3>
                    <p>- 100% verified property listings</p>
                    <p>- Dedicated relationship manager</p>
                    <p>- Assistance with home loans and legal paperwork</p>
                    <p>- End-to-end support from shortlisting to registration</p>
                </div>
            </div>
        </div>
    </section>

    <!-- ========== Footer ========== -->
    <footer>
        © 2025 DreamNest Real Estate. All rights reserved.
    </footer>

    <!-- ========== JavaScript for filters & form ========== -->
    <script>
        // ======== Property filter logic ========
        const applyFiltersBtn = document.getElementById('applyFiltersBtn');
        const locationFilter = document.getElementById('locationFilter');
        const typeFilter = document.getElementById('typeFilter');
        const minPriceInput = document.getElementById('minPrice');
        const maxPriceInput = document.getElementById('maxPrice');
        const propertyCards = document.querySelectorAll('.property-card');
        const resultsCount = document.getElementById('resultsCount');

        function applyFilters() {
            const locationValue = locationFilter.value;
            const typeValue = typeFilter.value;
            const minPrice = parseInt(minPriceInput.value) || 0;
            const maxPrice = parseInt(maxPriceInput.value) || Number.MAX_SAFE_INTEGER;

            let visibleCount = 0;

            propertyCards.forEach(card => {
                const cardLocation = card.getAttribute('data-location');
                const cardType = card.getAttribute('data-type');
                const cardPrice = parseInt(card.getAttribute('data-price'));

                const locationMatch = (locationValue === 'all' || locationValue === cardLocation);
                const typeMatch = (typeValue === 'all' || typeValue === cardType);
                const priceMatch = (cardPrice >= minPrice && cardPrice <= maxPrice);

                if (locationMatch && typeMatch && priceMatch) {
                    card.style.display = 'flex';
                    visibleCount++;
                } else {
                    card.style.display = 'none';
                }
            });

            resultsCount.textContent = visibleCount + ' result' + (visibleCount !== 1 ? 's' : '');
        }

        applyFiltersBtn.addEventListener('click', applyFilters);

        // Optional: auto-apply filters when user changes any option
        [locationFilter, typeFilter, minPriceInput, maxPriceInput].forEach(el => {
            el.addEventListener('change', applyFilters);
        });

        // ======== Inquiry form validation (basic) ========
        const inquiryForm = document.getElementById('inquiryForm');
        const successMessage = document.getElementById('successMessage');

        inquiryForm.addEventListener('submit', function (event) {
            event.preventDefault();

            const name = document.getElementById('name');
            const email = document.getElementById('email');
            const phone = document.getElementById('phone');

            // Clear previous styles
            [name, email, phone].forEach(input => {
                input.style.borderColor = '#ccc';
            });

            let isValid = true;

            if (name.value.trim() === '') {
                name.style.borderColor = 'red';
                isValid = false;
            }

            if (email.value.trim() === '' || !email.value.includes('@')) {
                email.style.borderColor = 'red';
                isValid = false;
            }

            if (phone.value.trim().length < 10) {
                phone.style.borderColor = 'red';
                isValid = false;
            }

            if (!isValid) {
                successMessage.style.display = 'none';
                return;
            }

            // Simulate form submission success
            successMessage.style.display = 'block';
            inquiryForm.reset();
        });
    </script>
</body>
</html>
