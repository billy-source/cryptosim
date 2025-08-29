# 🚀 Crypto Trading Simulation & Pro Platform (Django Backend)

This project is a **crypto trading platform backend built with Django**.  
It provides two modes:  

- **Simulation Mode (Beginners):**  
  Users start with **$100,000 virtual money** for practice trades.  

- **Pro Mode (Advanced Users):**  
  Real trading with **M-Pesa integration** (deposit & withdraw).  

The backend is API-driven (using Django REST Framework), making it easy to connect with a frontend (Django templates, React, Vue, etc.) or test using **Postman**.

---

## 📌 Features
- User authentication (register & login)  
- Automatic wallet creation on signup  
  - Beginners: `is_virtual=True`, balance = **100,000 USD**  
  - Pros: `is_virtual=False`, balance = **0 USD** (deposit required)  
- Trade API (buy/sell crypto with price simulation)  
- Balance updates after trades  
- Extendable for real crypto APIs or M-Pesa Daraja API for deposits/withdrawals  

---

## 🛠️ Tech Stack
- **Backend:** Django 4.x, Django REST Framework  
- **Database:** SQLite (default, switchable to PostgreSQL/MySQL)  
- **Auth:** Django’s built-in authentication system  
- **Payments (planned):** Safaricom M-Pesa Daraja API  

---

## 📂 Project Structure
crypto_project/
│── crypto_project/ # Main project settings
│ ├── settings.py
│ ├── urls.py
│ ├── wsgi.py
│
│── trading/ # Trading app
│ ├── models.py # Wallet & Trade models
│ ├── views.py # API endpoints
│ ├── urls.py # Trading routes
│
│── manage.py
│── README.md # Project documentation

yaml
Copy code

---

## 🚀 Installation & Setup

### 1. Clone the repo
```bash
git clone https://github.com/yourusername/crypto-trading-django.git
cd crypto-trading-django
2. Create & activate virtual environment
bash
Copy code
python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\activate      # Windows
3. Install dependencies
bash
Copy code
pip install -r requirements.txt
4. Run migrations
bash
Copy code
python manage.py makemigrations
python manage.py migrate
5. Create superuser (admin)
bash
Copy code
python manage.py createsuperuser
6. Run server
bash
Copy code
python manage.py runserver
🔌 API Endpoints
User Registration
POST /api/register/

json
Copy code
{
  "username": "john",
  "password": "1234"
}
➡️ Creates a new user + beginner wallet with $100,000.

Make Trade
POST /api/trade/

json
Copy code
{
  "user_id": 1,
  "symbol": "BTC",
  "amount": 0.01,
  "price": 50000,
  "side": "BUY"
}
➡️ Executes a trade and updates balance.

✅ Next Steps
Add trade history API (view all trades).

Add deposit & withdraw APIs (M-Pesa integration) for Pro users.



