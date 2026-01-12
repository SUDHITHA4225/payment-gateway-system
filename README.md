# Payment Gateway System

A containerized payment gateway system similar to Razorpay or Stripe.  
Supports merchant onboarding, order creation, UPI & card payments, hosted checkout page, and merchant dashboard.

---

## Features

- Merchant authentication using API Key & Secret
- Create and fetch payment orders
- UPI payment with VPA validation
- Card payment with Luhn algorithm validation
- Card network detection (Visa, Mastercard, Amex, RuPay)
- Simulated payment processing (success/failure)
- Hosted checkout page
- Merchant dashboard with real-time stats
- Fully Dockerized setup

---

## Tech Stack

- Backend: API service
- Frontend: React (Dashboard & Checkout)
- Database: PostgreSQL
- Containerization: Docker & Docker Compose

---

### Project Structure
payment-gateway-with-multi-method-processing/
├── backend/
├── frontend/
├── checkout-page/
├── Screenshots/
├── docker-compose.yml
├── .env.example
└── README.md

---

## Setup Instructions

### 1. Clone Repository
git clone https://github.com/SUDHITHA4225/payment-gateway-system.git
cd payment-gateway-system

### 2. Environment Setup
cp .env.example .env

### 3. Start Application
docker-compose up -d --build

### Service URLs

- API: http://localhost:8000
- Dashboard: http://localhost:3000
- Checkout Page: http://localhost:3001

### Test Merchant (Auto Seeded)	
- Email -	test@example.com
- API - Key	key_test_abc123
- API - Secret	secret_test_xyz789
Verify:
GET http://localhost:8000/api/v1/test/merchant

---

## API Endpoints
### Health Check
GET /health

### Create Order
POST /api/v1/orders
Headers:
X-Api-Key
X-Api-Secret

### Get Order
GET /api/v1/orders/{order_id}

### Create Payment
POST /api/v1/payments

### Get Payment
GET /api/v1/payments/{payment_id}

### Dashboard
- Login: /login
- Home: /dashboard
- Transactions: /dashboard/transactions

### Dashboard shows:
- API credentials
- Total transactions
- Total successful amount
- Success rate

---

### Checkout Page
#### Access:
http://localhost:3001/checkout?order_id=ORDER_ID

#### Flow:
- Fetch order details
- Select payment method (UPI / Card)
- Enter payment details
- Processing state
- Success or failure result


### Test Mode
Controlled via .env:
- TEST_MODE=true
- TEST_PAYMENT_SUCCESS=true
- TEST_PROCESSING_DELAY=1000
Used for deterministic evaluation.

### Screenshots
All required screenshots are available in the screenshots/ folder.

### Video Demo
Video link:
PASTE YOUR VIDEO LINK HERE

The video shows:
https://drive.google.com/file/d/14vuPcegTM6jvlp7n1GpvI22M4P83W3Rr/view?usp=sharing
- Order creation via API
- Checkout page payment
- Successful transaction
- Dashboard updates

---

 ## Summary

This project implements a complete payment gateway system with order creation, UPI and card payment processing.  
It includes a hosted checkout page, merchant dashboard, and secure API-based authentication.  
The entire system is fully Dockerized and runs with a single docker-compose command.
