Here is the complete, production-ready solution for Assignment 7.5 — Flexbox Mini-Project (Complete Responsive Landing Page).

This single, self-contained index.html file includes all 5 required sections (Navbar, Hero, 3 Feature Cards, Call-to-Action section, and Footer) styled consistently and built entirely using modern Flexbox principles.

Complete Code (index.html)
You can save this code as an index.html file on your computer, open it in any browser, and resize the window to test its full responsiveness.

HTML
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Assignment 7.5 — Flexbox Mini-Project Landing Page</title>
    <style>
        /* Global Reset & Consistent Typography */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #f8fafc;
            color: #1e293b;
            line-height: 1.6;
            overflow-x: hidden; /* Prevents horizontal overflow on smaller screens */
        }

        /* 1. Navigation Bar (Flexbox layout) */
        header {
            position: sticky;
            top: 0;
            background-color: #ffffff;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            z-index: 1000;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 5%;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            color: #2563eb;
            text-decoration: none;
        }

        .nav-links {
            list-style: none;
            display: flex;
            gap: 30px;
        }

        .nav-links a {
            text-decoration: none;
            color: #475569;
            font-weight: 500;
            transition: color 0.2s ease;
        }

        .nav-links a:hover {
            color: #2563eb;
        }

        .btn-nav {
            background-color: #2563eb;
            color: #ffffff;
            border: none;
            padding: 10px 20px;
            border-radius: 6px;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.2s ease;
        }

        .btn-nav:hover {
            background-color: #1d4ed8;
        }

        /* 2. Hero Section (Side-by-side Flexbox layout) */
        .hero-section {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 80px 5%;
            max-width: 1280px;
            margin: 0 auto;
            gap: 50px;
        }

        .hero-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
        }

        .hero-content h1 {
            font-size: 3rem;
            font-weight: 800;
            color: #0f172a;
            line-height: 1.2;
            margin-bottom: 20px;
        }

        .hero-content p {
            font-size: 1.15rem;
            color: #64748b;
            margin-bottom: 30px;
        }

        .btn-hero {
            background-color: #0f172a;
            color: #ffffff;
            border: none;
            padding: 14px 28px;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: background-color 0.2s ease;
        }

        .btn-hero:hover {
            background-color: #334155;
        }

        .hero-image {
            flex: 1;
            display: flex;
            justify-content: center;
        }

        .hero-image img {
            width: 100%;
            max-width: 500px;
            height: auto;
            border-radius: 12px;
            box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }

        /* 3. Feature Cards Section (Responsive row using Flexbox, flex-wrap, and gap) */
        .features-section {
            padding: 80px 5%;
            max-width: 1280px;
            margin: 0 auto;
            text-align: center;
        }

        .features-header h2 {
            font-size: 2.25rem;
            color: #0f172a;
            margin-bottom: 15px;
        }

        .features-header p {
            color: #64748b;
            font-size: 1.1rem;
            margin-bottom: 50px;
        }

        .features-container {
            display: flex;                  /* Activates Flexbox */
            flex-wrap: wrap;                /* Allows cards to wrap on smaller screens */
            justify-content: center;        /* Centers cards nicely */
            align-items: stretch;           /* Ensures cards match height */
            gap: 30px;                      /* Rule 3: Consistent gap spacing */
        }

        .feature-card {
            background: #ffffff;
            padding: 40px 30px;
            border-radius: 12px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
            flex: 1 1 300px;                /* Responsive sizing: grow, shrink, base width */
            max-width: 380px;
            text-align: left;
            border: 1px solid #e2e8f0;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .feature-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
        }

        .feature-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
        }

        .feature-card h3 {
            font-size: 1.25rem;
            color: #1e293b;
            margin-bottom: 12px;
        }

        .feature-card p {
            color: #64748b;
            font-size: 0.95rem;
        }

        /* 4. Call-to-Action (CTA) Section */
        .cta-section {
            background: linear-gradient(135deg, #2563eb, #1d4ed8);
            color: #ffffff;
            text-align: center;
            padding: 80px 20px;
            margin: 40px 0 0 0;
        }

        .cta-content {
            max-width: 700px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .cta-content h2 {
            font-size: 2.5rem;
            font-weight: 700;
        }

        .cta-content p {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        .btn-cta {
            background-color: #ffffff;
            color: #2563eb;
            border: none;
            padding: 14px 32px;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            margin-top: 10px;
            transition: background-color 0.2s ease;
        }

        .btn-cta:hover {
            background-color: #f1f5f9;
        }

        /* 5. Footer Section */
        footer {
            background-color: #0f172a;
            color: #94a3b8;
            text-align: center;
            padding: 40px 20px;
            font-size: 0.9rem;
        }

        /* Responsive Media Queries (Rule 5: No overflow on smaller screens) */
        @media (max-width: 900px) {
            .hero-section {
                flex-direction: column-reverse;
                text-align: center;
                padding: 40px 5%;
            }

            .hero-content {
                align-items: center;
            }

            .hero-content h1 {
                font-size: 2.2rem;
            }

            .nav-links {
                display: none; /* Collapses navigation links on small screens for clean mobile layout */
            }

            .cta-content h2 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

    <!-- 1. Navigation Bar -->
    <header>
        <a href="#" class="logo">SaaSFlow</a>
        <ul class="nav-links">
            <li><a href="#">Overview</a></li>
            <li><a href="#">Features</a></li>
            <li><a href="#">Pricing</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
        <button class="btn-nav">Get Started</button>
    </header>

    <!-- Main Container -->
    <main>
        <!-- 2. Hero Section -->
        <section class="hero-section">
            <div class="hero-content">
                <h1>Scale Your Business With Confidence</h1>
                <p>An all-in-one platform designed to streamline your workflow, boost productivity, and drive sustainable growth.</p>
                <button class="btn-hero">Start Your Free Trial</button>
            </div>
            <div class="hero-image">
                <img src="https://picsum.photos/seed/landinghero/600/450" alt="Product Dashboard Preview">
            </div>
        </section>

        <!-- 3. Feature Cards Section (3 Cards in a Responsive Flexbox Row) -->
        <section class="features-section">
            <div class="features-header">
                <h2>Built For Modern Teams</h2>
                <p>Everything you need to manage, track, and scale your projects effectively.</p>
            </div>
            <div class="features-container">
                <div class="feature-card">
                    <div class="feature-icon">⚡</div>
                    <h3>Lightning Fast</h3>
                    <p>Optimized performance ensures your team can work without lag, keeping efficiency at an all-time high.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🔒</div>
                    <h3>Enterprise Security</h3>
                    <p>Advanced data encryption and role-based access control keep your company’s sensitive assets completely safe.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">📊</div>
                    <h3>Real-time Analytics</h3>
                    <p>Gain deep visibility into your performance metrics with instant, automated reports and dashboards.</p>
                </div>
            </div>
        </section>

        <!-- 4. Call-to-Action Section -->
        <section class="cta-section">
            <div class="cta-content">
                <h2>Ready to transform your workflow?</h2>
                <p>Join thousands of high-performing teams already using SaaSFlow today.</p>
                <button class="btn-cta">Get Started For Free</button>
            </div>
        </section>
    </main>

    <!-- 5. Footer Section -->
    <footer>
        <p>&copy; 2026 SaaSFlow Inc. All rights reserved. Built with semantic HTML & CSS Flexbox.</p>
    </footer>

</body>
</html>
How to Prepare Your GitHub Submission:
Create a new folder on your computer named flexbox-mini-project.

Save the code above inside that folder as index.html.

Open GitHub in your browser, create a new public repository (e.g., named flexbox-mini-project), and upload your index.html file.

Submit your repository link along with screenshots of your landing page viewed at both Desktop and Mobile widths!