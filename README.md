<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Golden Egypt Tours - Discover Ancient Wonders</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;800&family=Open+Sans:wght@300;400;600;700&display=swap');
        
        :root {
            --gold: #D4AF37;
            --gold-light: #F4E4BC;
            --nile-blue: #1E3A5F;
            --desert-sand: #C2B280;
            --deep-blue: #0F2744;
            --white: #FFFFFF;
            --accent: #FF6B35;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Open Sans', sans-serif;
            background-color: var(--deep-blue);
            color: var(--white);
            line-height: 1.6;
        }
        
        h1, h2, h3, h4 {
            font-family: 'Cinzel', serif;
        }
        
        /* Navigation */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 1000;
            background: rgba(15, 39, 68, 0.95);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }
        
        .logo {
            font-family: 'Cinzel', serif;
            font-size: 1.8rem;
            font-weight: 800;
            color: var(--gold);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .logo::before {
            content: '☥';
            font-size: 2rem;
        }
        
        .nav-links {
            display: flex;
            gap: 40px;
            list-style: none;
        }
        
        .nav-links a {
            color: var(--white);
            text-decoration: none;
            font-weight: 600;
            position: relative;
            transition: color 0.3s;
            text-transform: uppercase;
            font-size: 0.9rem;
            letter-spacing: 1px;
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--gold);
            transition: width 0.3s;
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        .nav-links a:hover {
            color: var(--gold);
        }
        
        .nav-actions {
            display: flex;
            gap: 20px;
            align-items: center;
        }
        
        .btn-primary {
            background: var(--gold);
            color: var(--deep-blue);
            padding: 12px 30px;
            border: none;
            border-radius: 30px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1px;
        }
        
        .btn-primary:hover {
            background: var(--gold-light);
            transform: translateY(-2px);
            box-shadow: 0 5px 20px rgba(212, 175, 55, 0.4);
        }
        
        .cart-icon {
            position: relative;
            cursor: pointer;
            font-size: 1.5rem;
            color: var(--gold);
        }
        
        .cart-count {
            position: absolute;
            top: -10px;
            right: -10px;
            background: var(--accent);
            color: white;
            border-radius: 50%;
            width: 22px;
            height: 22px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.75rem;
            font-weight: bold;
        }
        
        /* Hero Section */
        .hero {
            height: 100vh;
            background: linear-gradient(135deg, rgba(15, 39, 68, 0.8), rgba(30, 58, 95, 0.6)), 
                        url('https://images.unsplash.com/photo-1539650116455-251d9a063595?w=1920') center/cover;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }
        
        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><circle cx="50" cy="50" r="40" fill="none" stroke="%23D4AF37" stroke-width="0.5" opacity="0.1"/></svg>');
            background-size: 200px;
            opacity: 0.3;
            animation: float 20s infinite linear;
        }
        
        @keyframes float {
            0% { transform: translateY(0) rotate(0deg); }
            100% { transform: translateY(-50px) rotate(360deg); }
        }
        
        .hero-content {
            z-index: 2;
            max-width: 900px;
            padding: 0 20px;
            animation: fadeInUp 1s ease;
        }
        
        .hero h1 {
            font-size: 4.5rem;
            margin-bottom: 20px;
            color: var(--gold-light);
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            line-height: 1.2;
        }
        
        .hero p {
            font-size: 1.4rem;
            margin-bottom: 40px;
            opacity: 0.9;
            font-weight: 300;
        }
        
        .hero-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .btn-secondary {
            background: transparent;
            color: var(--gold);
            padding: 12px 30px;
            border: 2px solid var(--gold);
            border-radius: 30px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            font-size: 0.85rem;
            letter-spacing: 1px;
            text-decoration: none;
        }
        
        .btn-secondary:hover {
            background: var(--gold);
            color: var(--deep-blue);
        }
        
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Search Section */
        .search-section {
            background: var(--nile-blue);
            padding: 40px;
            margin-top: -50px;
            position: relative;
            z-index: 100;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }
        
        .search-form {
            display: grid;
            grid-template-columns: repeat(4, 1fr) auto;
            gap: 20px;
            align-items: end;
        }
        
        .form-group {
            display: flex;
            flex-direction: column;
        }
        
        .form-group label {
            color: var(--gold);
            font-weight: 600;
            margin-bottom: 8px;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .form-group input,
        .form-group select {
            padding: 15px;
            border: 2px solid rgba(212, 175, 55, 0.3);
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s;
        }
        
        .form-group input:focus,
        .form-group select:focus {
            outline: none;
            border-color: var(--gold);
            background: rgba(255, 255, 255, 0.15);
        }
        
        .search-btn {
            background: var(--gold);
            color: var(--deep-blue);
            border: none;
            padding: 15px 40px;
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            font-size: 1rem;
        }
        
        .search-btn:hover {
            background: var(--gold-light);
            transform: scale(1.05);
        }
        
        /* Section Styles */
        section {
            padding: 100px 50px;
        }
        
        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }
        
        .section-header h2 {
            font-size: 2.8rem;
            color: var(--gold);
            margin-bottom: 15px;
        }
        
        .section-header p {
            color: rgba(255, 255, 255, 0.7);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }
        
        /* Attractions Grid */
        .attractions {
            background: linear-gradient(to bottom, var(--deep-blue), var(--nile-blue));
        }
        
        .attractions-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .attraction-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.4s;
            border: 1px solid rgba(212, 175, 55, 0.2);
            position: relative;
        }
        
        .attraction-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 30px 60px rgba(0,0,0,0.4);
            border-color: var(--gold);
        }
        
        .attraction-image {
            width: 100%;
            height: 250px;
            background-size: cover;
            background-position: center;
            position: relative;
        }
        
        .attraction-badge {
            position: absolute;
            top: 20px;
            right: 20px;
            background: var(--gold);
            color: var(--deep-blue);
            padding: 8px 16px;
            border-radius: 20px;
            font-weight: 700;
            font-size: 0.85rem;
        }
        
        .attraction-content {
            padding: 30px;
        }
        
        .attraction-content h3 {
            font-size: 1.5rem;
            color: var(--gold-light);
            margin-bottom: 10px;
        }
        
        .attraction-content p {
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 20px;
            line-height: 1.6;
        }
        
        .attraction-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .price {
            font-size: 1.5rem;
            color: var(--gold);
            font-weight: 700;
        }
        
        .rating {
            color: var(--gold);
        }
        
        .book-btn {
            width: 100%;
            padding: 15px;
            background: transparent;
            border: 2px solid var(--gold);
            color: var(--gold);
            border-radius: 10px;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .book-btn:hover {
            background: var(--gold);
            color: var(--deep-blue);
        }
        
        /* Activities Section */
        .activities {
            background: var(--deep-blue);
        }
        
        .activities-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 25px;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .activity-card {
            background: linear-gradient(135deg, rgba(212, 175, 55, 0.1), rgba(30, 58, 95, 0.3));
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.3s;
            border: 1px solid rgba(212, 175, 55, 0.2);
            cursor: pointer;
        }
        
        .activity-card:hover {
            transform: translateY(-5px);
            border-color: var(--gold);
            background: linear-gradient(135deg, rgba(212, 175, 55, 0.2), rgba(30, 58, 95, 0.4));
        }
        
        .activity-icon {
            font-size: 3rem;
            margin-bottom: 20px;
        }
        
        .activity-card h3 {
            color: var(--gold);
            margin-bottom: 10px;
            font-size: 1.3rem;
        }
        
        .activity-card p {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.95rem;
        }
        
        /* Hotels Section */
        .hotels {
            background: linear-gradient(to bottom, var(--nile-blue), var(--deep-blue));
        }
        
        .hotels-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        .hotel-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            overflow: hidden;
            border: 1px solid rgba(212, 175, 55, 0.2);
            transition: all 0.3s;
        }
        
        .hotel-card:hover {
            transform: scale(1.02);
            border-color: var(--gold);
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
        }
        
        .hotel-image {
            width: 100%;
            height: 200px;
            background-size: cover;
            background-position: center;
        }
        
        .hotel-content {
            padding: 25px;
        }
        
        .hotel-stars {
            color: var(--gold);
            margin-bottom: 10px;
            font-size: 1.2rem;
        }
        
        .hotel-content h3 {
            color: var(--gold-light);
            margin-bottom: 10px;
            font-size: 1.4rem;
        }
        
        .hotel-location {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.9rem;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 5px;
        }
        
        .hotel-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 20px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .hotel-price span {
            font-size: 1.3rem;
            color: var(--gold);
            font-weight: 700;
        }
        
        /* Guides Section */
        .guides {
            background: var(--deep-blue);
        }
        
        .guides-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .guide-card {
            text-align: center;
            padding: 30px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            border: 1px solid rgba(212, 175, 55, 0.2);
            transition: all 0.3s;
        }
        
        .guide-card:hover {
            transform: translateY(-10px);
            border-color: var(--gold);
        }
        
        .guide-avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--gold), var(--desert-sand));
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3rem;
            border: 4px solid var(--gold);
        }
        
        .guide-card h3 {
            color: var(--gold);
            margin-bottom: 5px;
        }
        
        .guide-card p {
            color: rgba(255, 255, 255, 0.7);
            font-size: 0.9rem;
            margin-bottom: 15px;
        }
        
        .guide-languages {
            display: flex;
            gap: 10px;
            justify-content: center;
            flex-wrap: wrap;
        }
        
        .lang-tag {
            background: rgba(212, 175, 55, 0.2);
            color: var(--gold);
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.8rem;
        }
        
        /* Booking Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.8);
            z-index: 3000;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(5px);
        }
        
        .modal.active {
            display: flex;
        }
        
        .modal-content {
            background: var(--nile-blue);
            border-radius: 20px;
            padding: 40px;
            max-width: 600px;
            width: 90%;
            max-height: 90vh;
            overflow-y: auto;
            border: 2px solid var(--gold);
            position: relative;
            animation: modalSlide 0.3s ease;
        }
        
        @keyframes modalSlide {
            from { transform: translateY(-50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        
        .modal-close {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 2rem;
            color: var(--gold);
            cursor: pointer;
            background: none;
            border: none;
        }
        
        .modal h2 {
            color: var(--gold);
            margin-bottom: 20px;
            font-size: 1.8rem;
        }
        
        .booking-form .form-group {
            margin-bottom: 20px;
        }
        
        .booking-form label {
            display: block;
            color: var(--gold);
            margin-bottom: 8px;
            font-weight: 600;
        }
        
        .booking-form input,
        .booking-form select,
        .booking-form textarea {
            width: 100%;
            padding: 12px;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(212, 175, 55, 0.3);
            color: white;
            border-radius: 10px;
            font-size: 1rem;
        }
        
        .booking-form input:focus,
        .booking-form select:focus,
        .booking-form textarea:focus {
            outline: none;
            border-color: var(--gold);
        }
        
        .booking-summary {
            background: rgba(212, 175, 55, 0.1);
            padding: 20px;
            border-radius: 10px;
            margin: 20px 0;
            border: 1px solid var(--gold);
        }
        
        .booking-summary h4 {
            color: var(--gold);
            margin-bottom: 10px;
        }
        
        .summary-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            color: rgba(255, 255, 255, 0.8);
        }
        
        .summary-total {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 2px solid var(--gold);
            font-weight: 700;
            font-size: 1.2rem;
            color: var(--gold);
        }
        
        .confirm-booking {
            width: 100%;
            padding: 15px;
            background: var(--gold);
            color: var(--deep-blue);
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .confirm-booking:hover {
            background: var(--gold-light);
            transform: scale(1.02);
        }
        
        /* Cart Sidebar */
        .cart-sidebar {
            position: fixed;
            top: 0;
            right: -450px;
            width: 450px;
            height: 100vh;
            background: var(--nile-blue);
            box-shadow: -10px 0 30px rgba(0,0,0,0.5);
            transition: right 0.3s ease;
            z-index: 2000;
            padding: 30px;
            overflow-y: auto;
            border-left: 3px solid var(--gold);
        }
        
        .cart-sidebar.open {
            right: 0;
        }
        
        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 2px solid var(--gold);
        }
        
        .cart-header h2 {
            color: var(--gold);
            font-size: 1.8rem;
        }
        
        .close-cart {
            background: none;
            border: none;
            color: var(--gold);
            font-size: 2.5rem;
            cursor: pointer;
        }
        
        .cart-item {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 15px;
            border: 1px solid rgba(212, 175, 55, 0.3);
        }
        
        .cart-item-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 10px;
        }
        
        .cart-item h4 {
            color: var(--gold-light);
            font-size: 1.2rem;
        }
        
        .cart-item-type {
            color: rgba(255, 255, 255, 0.6);
            font-size: 0.85rem;
            margin-bottom: 10px;
        }
        
        .cart-item-details {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .quantity-control {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .qty-btn {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            border: 1px solid var(--gold);
            background: transparent;
            color: var(--gold);
            cursor: pointer;
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .cart-item-price {
            color: var(--gold);
            font-weight: 700;
            font-size: 1.1rem;
        }
        
        .remove-item {
            background: var(--accent);
            color: white;
            border: none;
            padding: 5px 12px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 0.8rem;
        }
        
        .cart-total-section {
            margin-top: 30px;
            padding-top: 20px;
            border-top: 2px solid var(--gold);
        }
        
        .cart-total-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            color: rgba(255, 255, 255, 0.8);
        }
        
        .cart-total-final {
            display: flex;
            justify-content: space-between;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 1px solid rgba(212, 175, 55, 0.3);
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--gold);
        }
        
        .checkout-btn {
            width: 100%;
            padding: 18px;
            background: var(--gold);
            color: var(--deep-blue);
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: 700;
            cursor: pointer;
            margin-top: 20px;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
        
        .checkout-btn:hover {
            background: var(--gold-light);
            transform: scale(1.02);
        }
        
        .overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.7);
            display: none;
            z-index: 1500;
        }
        
        .overlay.active {
            display: block;
        }
        
        /* Footer */
        footer {
            background: #0a1929;
            padding: 60px 50px 30px;
            border-top: 3px solid var(--gold);
        }
        
        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-section h3 {
            color: var(--gold);
            margin-bottom: 20px;
            font-size: 1.3rem;
        }
        
        .footer-section p,
        .footer-section a {
            color: rgba(255, 255, 255, 0.7);
            text-decoration: none;
            line-height: 2;
            transition: color 0.3s;
        }
        
        .footer-section a:hover {
            color: var(--gold);
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }
        
        .social-links a {
            width: 45px;
            height: 45px;
            background: rgba(212, 175, 55, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.3rem;
            transition: all 0.3s;
        }
        
        .social-links a:hover {
            background: var(--gold);
            transform: translateY(-5px);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid rgba(212, 175, 55, 0.2);
            color: rgba(255, 255, 255, 0.5);
        }
        
        /* Responsive */
        @media (max-width: 1024px) {
            .search-form {
                grid-template-columns: 1fr 1fr;
            }
            .footer-content {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        
        @media (max-width: 768px) {
            .nav-links { display: none; }
            .hero h1 { font-size: 2.5rem; }
            .search-form { grid-template-columns: 1fr; }
            .search-btn { grid-column: 1; }
            section { padding: 60px 20px; }
            .cart-sidebar { width: 100%; right: -100%; }
            .footer-content { grid-template-columns: 1fr; }
        }
        
        /* Scroll Animations */
        .scroll-reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.6s ease;
        }
        
        .scroll-reveal.visible {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* Loading State */
        .loading {
            display: inline-block;
            width: 20px;
            height: 20px;
            border: 3px solid rgba(212, 175, 55, 0.3);
            border-radius: 50%;
            border-top-color: var(--gold);
            animation: spin 1s ease-in-out infinite;
        }
        
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <!-- Navigation -->
    <nav id="navbar">
        <a href="#" class="logo">Golden Egypt Tours</a>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#attractions">Sites</a></li>
            <li><a href="#activities">Adventures</a></li>
            <li><a href="#hotels">Hotels</a></li>
            <li><a href="#guides">Guides</a></li>
        </ul>
        <div class="nav-actions">
            <div class="cart-icon" onclick="toggleCart()">
                🛒
                <span class="cart-count" id="cartCount">0</span>
            </div>
            <button class="btn-primary" onclick="scrollToBooking()">Book Now</button>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="hero-content">
            <h1>Discover the Land of Pharaohs</h1>
            <p>Journey through 5,000 years of history. From the Great Pyramids to the crystal waters of the Red Sea, experience Egypt's golden treasures.</p>
            <div class="hero-buttons">
                <a href="#attractions" class="btn-primary">Explore Sites</a>
                <a href="#activities" class="btn-secondary">View Activities</a>
            </div>
        </div>
    </section>

    <!-- Search Section -->
    <div class="search-section">
        <form class="search-form" onsubmit="handleSearch(event)">
            <div class="form-group">
                <label>Destination</label>
                <select id="searchDestination">
                    <option value="">All Locations</option>
                    <option value="cairo">Cairo & Giza</option>
                    <option value="luxor">Luxor</option>
                    <option value="aswan">Aswan</option>
                    <option value="alexandria">Alexandria</option>
                    <option value="redsea">Red Sea</option>
                </select>
            </div>
            <div class="form-group">
                <label>Date</label>
                <input type="date" id="searchDate">
            </div>
            <div class="form-group">
                <label>Travelers</label>
                <select id="searchTravelers">
                    <option value="1">1 Person</option>
                    <option value="2">2 People</option>
                    <option value="3">3 People</option>
                    <option value="4">4+ People</option>
                </select>
            </div>
            <div class="form-group">
                <label>Type</label>
                <select id="searchType">
                    <option value="">All Types</option>
                    <option value="historical">Historical</option>
                    <option value="adventure">Adventure</option>
                    <option value="relaxation">Relaxation</option>
                </select>
            </div>
            <button type="submit" class="search-btn">Search</button>
        </form>
    </div>

    <!-- Attractions Section -->
    <section class="attractions" id="attractions">
        <div class="section-header scroll-reveal">
            <h2>Historical Sites & Attractions</h2>
            <p>Walk in the footsteps of pharaohs and explore ancient wonders that have stood for millennia</p>
        </div>
        <div class="attractions-grid">
            <div class="attraction-card scroll-reveal">
                <div class="attraction-image" style="background-image: url('https://images.unsplash.com/photo-1503177119275-0aa32b3a9368?w=800');">
                    <span class="attraction-badge">Popular</span>
                </div>
                <div class="attraction-content">
                    <h3>Great Pyramids of Giza</h3>
                    <p>Stand before the last remaining wonder of the ancient world. Includes Sphinx and Valley Temple access with expert Egyptologist guide.</p>
                    <div class="attraction-meta">
                        <span class="price">$85</span>
                        <span class="rating">★★★★★ (2.4k reviews)</span>
                    </div>
                    <button class="book-btn" onclick="openBooking('Great Pyramids of Giza', 85, 'attraction')">Book Experience</button>
                </div>
            </div>

            <div class="attraction-card scroll-reveal">
                <div class="attraction-image" style="background-image: url('https://images.unsplash.com/photo-1568322445389-f64ac2515020?w=800');">
                    <span class="attraction-badge">Must See</span>
                </div>
                <div class="attraction-content">
                    <h3>Valley of the Kings</h3>
                    <p>Explore the royal necropolis of Luxor. Visit Tutankhamun's tomb and colorful burial chambers of ancient pharaohs.</p>
                    <div class="attraction-meta">
                        <span class="price">$65</span>
                        <span class="rating">★★★★★ (1.8k reviews)</span>
                    </div>
                    <button class="book-btn" onclick="openBooking('Valley of the Kings', 65, 'attraction')">Book Experience</button>
                </div>
            </div>

            <div class="attraction-card scroll-reveal">
                <div class="attraction-image" style="background-image: url('https://images.unsplash.com/photo-1542259681-d4cd3839bb44?w=800');">
                    <span class="attraction-badge">UNESCO</span>
                </div>
                <div class="attraction-content">
                    <h3>Abu Simbel Temples</h3>
                    <p>Marvel at Ramses II's monumental temples. Optional sunrise visit with sound and light show experience.</p>
                    <div class="attraction-meta">
                        <span class="price">$120</span>
                        <span class="rating">★★★★★ (956 reviews)</span>
                    </div>
                    <button class="book-btn" onclick="openBooking('Abu Simbel Temples', 120, 'attraction')">Book Experience</button>
                </div>
            </div>

            <div class="attraction-card scroll-reveal">
                <div class="attraction-image" style="background-image: url('https://images.unsplash.com/photo-1553913861-c0fddf2619ee?w=800');">
                    <span class="attraction-badge">New</span>
                </div>
                <div class="attraction-content">
                    <h3>Grand Egyptian Museum</h3>
                    <p>The world's largest archaeological museum. Home to the complete Tutankhamun collection and 100,000+ artifacts.</p>
                    <div class="attraction-meta">
                        <span class="price">$45</span>
                        <span class="rating">★★★★★ (3.2k reviews)</span>
                    </div>
                    <button class="book-btn" onclick="openBooking('Grand Egyptian Museum', 45, 'attraction')">Book Experience</button>
                </div>
            </div>

            <div class="attraction-card scroll-reveal">
                <div class="attraction-image" style="background-image: url('https://images.unsplash.com/photo-1572252009286-268acec5ca0a?w=800');">
                    <span class="attraction-badge">Adventure</span>
                </div>
                <div class="attraction-content">
                    <h3>Karnak Temple Complex</h3>
                    <p>The world's largest ancient religious site. Hypostyle Hall with 134 massive columns and sacred lake.</p>
                    <div class="attraction-meta">
                        <span class="price">$55</span>
                        <span class="rating">★★★★★ (1.5k reviews)</span>
                    </div>
                    <button class="book-btn" onclick="openBooking('Karnak Temple Complex', 55, 'attraction')">Book Experience</button>
                </div>
            </div>

            <div class="attraction-card scroll-reveal">
                <div class="attraction-image" style="background-image: url('https://images.unsplash.com/photo-1590523277543-a94d2e4eb00b?w=800');">
                    <span class="attraction-badge">Relaxing</span>
                </div>
                <div class="attraction-content">
                    <h3>Felucca on the Nile</h3>
                    <p>Sail the world's longest river on a traditional wooden sailboat. Sunset cruise with Egyptian tea and snacks.</p>
                    <div class="attraction-meta">
                        <span class="price">$35</span>
                        <span class="rating">★★★★☆ (892 reviews)</span>
                    </div>
                    <button class="book-btn" onclick="openBooking('Felucca Nile Cruise', 35, 'attraction')">Book Experience</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Activities Section -->
    <section class="activities" id="activities">
        <div class="section-header scroll-reveal">
            <h2>Adventures & Activities</h2>
            <p>From desert safaris to diving in coral reefs, discover Egypt's diverse landscapes</p>
        </div>
        <div class="activities-grid">
            <div class="activity-card scroll-reveal" onclick="openBooking('Desert Safari', 95, 'activity')">
                <div class="activity-icon">🏜️</div>
                <h3>Desert Safari</h3>
                <p>4x4 jeep adventure through the White Desert. Camp under stars, Bedouin dinner, and sunrise camel ride.</p>
            </div>

            <div class="activity-card scroll-reveal" onclick="openBooking('Red Sea Diving', 110, 'activity')">
                <div class="activity-icon">🤿</div>
                <h3>Red Sea Diving</h3>
                <p>World-class diving in Sharm El-Sheikh. Two dives with equipment, lunch, and PADI-certified instructor.</p>
            </div>

            <div class="activity-card scroll-reveal" onclick="openBooking('Hot Air Balloon', 150, 'activity')">
                <div class="activity-icon">🎈</div>
                <h3>Hot Air Balloon</h3>
                <p>Sunrise balloon ride over Luxor's west bank. Aerial views of temples, valleys, and the Nile.</p>
            </div>

            <div class="activity-card scroll-reveal" onclick="openBooking('Nile Cruise', 280, 'activity')">
                <div class="activity-icon">🚢</div>
                <h3>Nile Cruise</h3>
                <p>3-night luxury cruise from Aswan to Luxor. All meals, guided tours, and entertainment included.</p>
            </div>

            <div class="activity-card scroll-reveal" onclick="openBooking('Siwa Oasis', 180, 'activity')">
                <div class="activity-icon">🏝️</div>
                <h3>Siwa Oasis</h3>
                <p>2-day trip to the legendary oasis. Salt lakes, Cleopatra's Bath, and ancient Oracle Temple.</p>
            </div>

            <div class="activity-card scroll-reveal" onclick="openBooking('Camel Market', 40, 'activity')">
                <div class="activity-icon">🐪</div>
                <h3>Birqash Camel Market</h3>
                <p>Authentic cultural experience at Cairo's famous Friday camel market. Local guide and transport.</p>
            </div>

            <div class="activity-card scroll-reveal" onclick="openBooking('Kite Surfing', 85, 'activity')">
                <div class="activity-icon">🏄</div>
                <h3>Kite Surfing</h3>
                <p>Lessons in El Gouna, the kite surfing capital. Equipment rental and 3-hour beginner course.</p>
            </div>

            <div class="activity-card scroll-reveal" onclick="openBooking('Cooking Class', 60, 'activity')">
                <div class="activity-icon">👨‍🍳</div>
                <h3>Egyptian Cooking</h3>
                <p>Learn to make koshari, falafel, and baklava. Market tour, cooking class, and dinner included.</p>
            </div>
        </div>
    </section>

    <!-- Hotels Section -->
    <section class="hotels" id="hotels">
        <div class="section-header scroll-reveal">
            <h2>Accommodations</h2>
            <p>From luxury resorts overlooking the Nile to boutique hotels in historic districts</p>
        </div>
        <div class="hotels-grid">
            <div class="hotel-card scroll-reveal">
                <div class="hotel-image" style="background-image: url('https://images.unsplash.com/photo-1566073771259-6a8506099945?w=800');"></div>
                <div class="hotel-content">
                    <div class="hotel-stars">★★★★★</div>
                    <h3>Marriott Mena House</h3>
                    <div class="hotel-location">📍 Giza - Pyramids View</div>
                    <p>Historic luxury hotel with direct pyramid views. Built in 1869, hosted kings and celebrities.</p>
                    <div class="hotel-price">
                        <span>$280/night</span>
                        <button class="btn-primary" onclick="openBooking('Marriott Mena House', 280, 'hotel')">Book</button>
                    </div>
                </div>
            </div>

            <div class="hotel-card scroll-reveal">
                <div class="hotel-image" style="background-image: url('https://images.unsplash.com/photo-1582719508461-905c673771fd?w=800');"></div>
                <div class="hotel-content">
                    <div class="hotel-stars">★★★★★</div>
                    <h3>Old Cataract Hotel</h3>
                    <div class="hotel-location">📍 Aswan - Nile River</div>
                    <p>Victorian-era palace where Agatha Christie wrote "Death on the Nile". Stunning Nile views.</p>
                    <div class="hotel-price">
                        <span>$350/night</span>
                        <button class="btn-primary" onclick="openBooking('Old Cataract Hotel', 350, 'hotel')">Book</button>
                    </div>
                </div>
            </div>

            <div class="hotel-card scroll-reveal">
                <div class="hotel-image" style="https://images.unsplash.com/photo-1520250497591-112f2f40a3f4?w=800');"></div>
                <div class="hotel-content">
                    <div class="hotel-stars">★★★★☆</div>
                    <h3>Hilton Luxor Resort</h3>
                    <div class="hotel-location">📍 Luxor - West Bank</div>
                    <p>Modern resort with spa, multiple pools, and views of the Theban Necropolis across the Nile.</p>
                    <div class="hotel-price">
                        <span>$145/night</span>
                        <button class="btn-primary" onclick="openBooking('Hilton Luxor', 145, 'hotel')">Book</button>
                    </div>
                </div>
            </div>

            <div class="hotel-card scroll-reveal">
                <div class="hotel-image" style="background-image: url('https://images.unsplash.com/photo-1571896349842-33c89424de2d?w=800');"></div>
                <div class="hotel-content">
                    <div class="hotel-stars">★★★★★</div>
                    <h3>Four Seasons Sharm</h3>
                    <div class="hotel-location">📍 Sharm El-Sheikh - Red Sea</div>
                    <p>Beachfront luxury with private marina, diving center, and views of Tiran Island.</p>
                    <div class="hotel-price">
                        <span>$420/night</span>
                        <button class="btn-primary" onclick="openBooking('Four Seasons Sharm', 420, 'hotel')">Book</button>
                    </div>
                </div>
            </div>

            <div class="hotel-card scroll-reveal">
                <div class="hotel-image" style="background-image: url('https://images.unsplash.com/photo-1551882547-ff40c8868f16?w=800');"></div>
                <div class="hotel-content">
                    <div class="hotel-stars">★★★★☆</div>
                    <h3>Windsor Hotel Cairo</h3>
                    <div class="hotel-location">📍 Downtown Cairo</div>
                    <p>Art Deco heritage hotel from 1906. Walk to Egyptian Museum, Khan el-Khalili bazaar.</p>
                    <div class="hotel-price">
                        <span>$95/night</span>
                        <button class="btn-primary" onclick="openBooking('Windsor Hotel', 95, 'hotel')">Book</button>
                    </div>
                </div>
            </div>

            <div class="hotel-card scroll-reveal">
                <div class="hotel-image" style="background-image: url('https://images.unsplash.com/photo-1445019980597-93fa8acb246c?w=800');"></div>
                <div class="hotel-content">
                    <div class="hotel-stars">★★★★★</div>
                    <h3>Oberoi Zahra</h3>
                    <div class="hotel-location">📍 Nile Cruise Ship</div>
                    <p>Luxury Nile cruiser with only 27 suites. Fine dining, spa, and personalized butler service.</p>
                    <div class="hotel-price">
                        <span>$680/night</span>
                        <button class="btn-primary" onclick="openBooking('Oberoi Zahra Cruise', 680, 'hotel')">Book</button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Guides Section -->
    <section class="guides" id="guides">
        <div class="section-header scroll-reveal">
            <h2>Expert Egyptologists</h2>
            <p>Our certified guides bring history to life with passion and deep knowledge</p>
        </div>
        <div class="guides-grid">
            <div class="guide-card scroll-reveal">
                <div class="guide-avatar">👨‍🏫</div>
                <h3>Ahmed Hassan</h3>
                <p>Senior Egyptologist • 15 years experience</p>
                <p style="font-size: 0.9rem; margin: 15px 0;">Specialist in pyramid archaeology and ancient Egyptian religion</p>
                <div class="guide-languages">
                    <span class="lang-tag">English</span>
                    <span class="lang-tag">Arabic</span>
                    <span class="lang-tag">French</span>
                </div>
            </div>

            <div class="guide-card scroll-reveal">
                <div class="guide-avatar">👩‍🏫</div>
                <h3>Sarah El-Masry</h3>
                <p>Art Historian • 12 years experience</p>
                <p style="font-size: 0.9rem; margin: 15px 0;">Expert in tomb paintings, hieroglyphics, and ancient art</p>
                <div class="guide-languages">
                    <span class="lang-tag">English</span>
                    <span class="lang-tag">German</span>
                    <span class="lang-tag">Italian</span>
                </div>
            </div>

            <div class="guide-card scroll-reveal">
                <div class="guide-avatar">👨‍🏫</div>
                <h3>Omar Farouk</h3>
                <p>Archaeologist • 20 years experience</p>
                <p style="font-size: 0.9rem; margin: 15px 0;">Led excavations in Luxor and Saqqara, published researcher</p>
                <div class="guide-languages">
                    <span class="lang-tag">English</span>
                    <span class="lang-tag">Spanish</span>
                    <span class="lang-tag">Russian</span>
                </div>
            </div>

            <div class="guide-card scroll-reveal">
                <div class="guide-avatar">👩‍🏫</div>
                <h3>Layla Ibrahim</h3>
                <p>Cultural Guide • 8 years experience</p>
                <p style="font-size: 0.9rem; margin: 15px 0;">Specializes in Coptic Cairo, Islamic architecture, and modern Egypt</p>
                <div class="guide-languages">
                    <span class="lang-tag">English</span>
                    <span class="lang-tag">Chinese</span>
                    <span class="lang-tag">Japanese</span>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="footer-content">
            <div class="footer-section">
                <h3>Golden Egypt Tours</h3>
                <p>Your gateway to the wonders of ancient Egypt. Licensed tour operator since 1998.</p>
                <div class="social-links">
                    <a href="#">📘</a>
                    <a href="#">📸</a>
                    <a href="#">🐦</a>
                    <a href="#">▶️</a>
                </div>
            </div>
            <div class="footer-section">
                <h3>Quick Links</h3>
                <a href="#attractions">Attractions</a><br>
                <a href="#activities">Activities</a><br>
                <a href="#hotels">Hotels</a><br>
                <a href="#guides">Guides</a>
            </div>
            <div class="footer-section">
                <h3>Contact</h3>
                <p>📍 12 Tahrir Square, Cairo</p>
                <p>📞 +20 2 1234 5678</p>
                <p>✉️ info@goldenegypttours.com</p>
            </div>
            <div class="footer-section">
                <h3>Legal</h3>
                <a href="#">Terms of Service</a><br>
                <a href="#">Privacy Policy</a><br>
                <a href="#">Cancellation Policy</a><br>
                <a href="#">Travel Insurance</a>
            </div>
        </div>
        <div class="footer-bottom">
            <p>&copy; 2024 Golden Egypt Tours. All rights reserved. | Licensed by the Egyptian Ministry of Tourism</p>
        </div>
    </footer>

    <!-- Booking Modal -->
    <div class="modal" id="bookingModal">
        <div class="modal-content">
            <button class="modal-close" onclick="closeBooking()">&times;</button>
            <h2 id="modalTitle">Book Experience</h2>
            <form class="booking-form" onsubmit="confirmBooking(event)">
                <div class="form-group">
                    <label>Full Name</label>
                    <input type="text" id="bookName" required>
                </div>
                <div class="form-group">
                    <label>Email</label>
                    <input type="email" id="bookEmail" required>
                </div>
                <div class="form-group">
                    <label>Phone</label>
                    <input type="tel" id="bookPhone" required>
                </div>
                <div class="form-group">
                    <label>Preferred Date</label>
                    <input type="date" id="bookDate" required>
                </div>
                <div class="form-group">
                    <label>Number of Travelers</label>
                    <select id="bookTravelers" onchange="updateModalTotal()">
                        <option value="1">1 Person</option>
                        <option value="2">2 People</option>
                        <option value="3">3 People</option>
                        <option value="4">4 People</option>
                        <option value="5">5+ People</option>
                    </select>
                </div>
                <div class="form-group">
                    <label>Special Requests</label>
                    <textarea id="bookNotes" rows="3" placeholder="Dietary requirements, accessibility needs, etc."></textarea>
                </div>
                
                <div class="booking-summary">
                    <h4>Booking Summary</h4>
                    <div class="summary-row">
                        <span id="summaryItem">Item</span>
                        <span id="summaryPrice">$0</span>
                    </div>
                    <div class="summary-row">
                        <span>Travelers</span>
                        <span id="summaryTravelers">1</span>
                    </div>
                    <div class="summary-total">
                        <span>Total</span>
                        <span id="summaryTotal">$0</span>
                    </div>
                </div>
                
                <button type="submit" class="confirm-booking">Confirm Booking</button>
            </form>
        </div>
    </div>

    <!-- Cart Sidebar -->
    <div class="overlay" id="overlay" onclick="toggleCart()"></div>
    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h2>Your Journey</h2>
            <button class="close-cart" onclick="toggleCart()">&times;</button>
        </div>
        <div id="cartItems">
            <p style="text-align: center; color: rgba(255,255,255,0.5); padding: 40px;">Your cart is empty. Start exploring Egypt!</p>
        </div>
        <div class="cart-total-section" id="cartTotalSection" style="display: none;">
            <div class="cart-total-row">
                <span>Subtotal</span>
                <span id="cartSubtotal">$0</span>
            </div>
            <div class="cart-total-row">
                <span>Taxes & Fees (10%)</span>
                <span id="cartTax">$0</span>
            </div>
            <div class="cart-total-final">
                <span>Total</span>
                <span id="cartTotal">$0</span>
            </div>
            <button class="checkout-btn" onclick="checkout()">Proceed to Checkout</button>
        </div>
    </div>

    <script>
        // Shopping Cart Logic
        let cart = [];
        let currentBooking = null;
        
        function openBooking(itemName, price, type) {
            currentBooking = { name: itemName, price: price, type: type };
            document.getElementById('modalTitle').textContent = type === 'hotel' ? 'Book Accommodation' : 'Book Experience';
            document.getElementById('summaryItem').textContent = itemName;
            document.getElementById('summaryPrice').textContent = '$' + price;
            updateModalTotal();
            document.getElementById('bookingModal').classList.add('active');
            document.body.style.overflow = 'hidden';
        }
        
        function closeBooking() {
            document.getElementById('bookingModal').classList.remove('active');
            document.body.style.overflow = 'auto';
            currentBooking = null;
        }
        
        function updateModalTotal() {
            if (!currentBooking) return;
            const travelers = parseInt(document.getElementById('bookTravelers').value);
            const total = currentBooking.price * travelers;
            document.getElementById('summaryTravelers').textContent = travelers + (travelers === 1 ? ' Person' : ' People');
            document.getElementById('summaryTotal').textContent = '$' + total;
        }
        
        function confirmBooking(e) {
            e.preventDefault();
            if (!currentBooking) return;
            
            const travelers = parseInt(document.getElementById('bookTravelers').value);
            const booking = {
                ...currentBooking,
                travelers: travelers,
                total: currentBooking.price * travelers,
                date: document.getElementById('bookDate').value,
                id: Date.now()
            };
            
            cart.push(booking);
            updateCart();
            closeBooking();
            
            // Show success message
            alert(`✅ Added to cart!\n\n${booking.name}\n${booking.travelers} traveler(s) - $${booking.total}\n\nClick the cart icon to review and checkout.`);
            
            // Reset form
            e.target.reset();
        }
        
        function updateCart() {
            const cartCount = document.getElementById('cartCount');
            const cartItems = document.getElementById('cartItems');
            const cartTotalSection = document.getElementById('cartTotalSection');
            
            cartCount.textContent = cart.length;
            
            if (cart.length === 0) {
                cartItems.innerHTML = '<p style="text-align: center; color: rgba(255,255,255,0.5); padding: 40px;">Your cart is empty. Start exploring Egypt!</p>';
                cartTotalSection.style.display = 'none';
            } else {
                cartItems.innerHTML = cart.map((item, index) => `
                    <div class="cart-item">
                        <div class="cart-item-header">
                            <div>
                                <h4>${item.name}</h4>
                                <div class="cart-item-type">${item.type.charAt(0).toUpperCase() + item.type.slice(1)} • ${item.date}</div>
                            </div>
                            <button class="remove-item" onclick="removeFromCart(${index})">Remove</button>
                        </div>
                        <div class="cart-item-details">
                            <div class="quantity-control">
                                <button class="qty-btn" onclick="updateQuantity(${index}, -1)">-</button>
                                <span>${item.travelers}</span>
                                <button class="qty-btn" onclick="updateQuantity(${index}, 1)">+</button>
                            </div>
                            <span class="cart-item-price">$${item.total}</span>
                        </div>
                    </div>
                `).join('');
                
                const subtotal = cart.reduce((sum, item) => sum + item.total, 0);
                const tax = subtotal * 0.1;
                const total = subtotal + tax;
                
                document.getElementById('cartSubtotal').textContent = '$' + subtotal;
                document.getElementById('cartTax').textContent = '$' + tax.toFixed(0);
                document.getElementById('cartTotal').textContent = '$' + total.toFixed(0);
                cartTotalSection.style.display = 'block';
            }
        }
        
        function updateQuantity(index, change) {
            const item = cart[index];
            const newTravelers = item.travelers + change;
            if (newTravelers < 1) return;
            if (newTravelers > 10) return;
            
            item.travelers = newTravelers;
            item.total = item.price * newTravelers;
            updateCart();
        }
        
        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCart();
        }
        
        function toggleCart() {
            const sidebar = document.getElementById('cartSidebar');
            const overlay = document.getElementById('overlay');
            sidebar.classList.toggle('open');
            overlay.classList.toggle('active');
            document.body.style.overflow = sidebar.classList.contains('open') ? 'hidden' : 'auto';
        }
        
        function checkout() {
            if (cart.length === 0) {
                alert('Your cart is empty!');
                return;
            }
            
            const total = cart.reduce((sum, item) => sum + item.total, 0);
            const tax = total * 0.1;
            const finalTotal = total + tax;
            
            alert(`🎉 Thank you for booking with Golden Egypt Tours!\n\nTotal Amount: $${finalTotal.toFixed(0)}\n\nYou will receive a confirmation email shortly with your detailed itinerary and e-tickets.\n\nGet ready for an unforgettable journey through ancient Egypt!`);
            
            cart = [];
            updateCart();
            toggleCart();
        }
        
        function handleSearch(e) {
            e.preventDefault();
            const destination = document.getElementById('searchDestination').value;
            const date = document.getElementById('searchDate').value;
            const type = document.getElementById('searchType').value;
            
            // Scroll to attractions and filter (simplified)
            document.getElementById('attractions').scrollIntoView({ behavior: 'smooth' });
            
            // In a real app, this would filter the results
            alert(`Searching for ${type || 'all'} experiences in ${destination || 'all locations'}${date ? ' on ' + date : ''}...`);
        }
        
        function scrollToBooking() {
            document.getElementById('attractions').scrollIntoView({ behavior: 'smooth' });
        }
        
        // Scroll Animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);
        
        document.querySelectorAll('.scroll-reveal').forEach(el => observer.observe(el));
        
        // Navbar scroll effect
        window.addEventListener('scroll', () => {
            const navbar = document.getElementById('navbar');
            if (window.scrollY > 50) {
                navbar.style.padding = '15px 50px';
                navbar.style.background = 'rgba(15, 39, 68, 0.98)';
            } else {
                navbar.style.padding = '20px 50px';
                navbar.style.background = 'rgba(15, 39, 68, 0.95)';
            }
        });
        
        // Set minimum date to today
        document.getElementById('searchDate').min = new Date().toISOString().split('T')[0];
        document.getElementById('bookDate').min = new Date().toISOString().split('T')[0];
        
        // Initialize
        updateCart();
    </script>
</body>
</html># golden-egypt-tours
