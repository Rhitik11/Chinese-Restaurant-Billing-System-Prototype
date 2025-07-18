# 🍜 Chinese Restaurant Billing System

This is a prototype of a real-world freelancing project developed using **Python Django** for efficiently handling restaurant orders, generating bills, and sending invoices via SMS. The system is designed for restaurants with high daily footfall and aims to automate billing and menu operations.

---

## 🚀 Tech Stack

- **Backend:** Python, Django  
- **Frontend:** HTML, CSS, Bootstrap, JavaScript  
- **Database:** SQLite3  
- **Third-Party Integration:** Twilio API (for sending SMS bills)  

---

## 📁 Project Structure

restaurant_billing/
├── manage.py
├── restaurant_billing/
│ └── settings, urls, wsgi
├── menu/
│ ├── models.py # Models: FoodItem, Order, OrderItem
│ ├── views.py # Order creation, billing, SMS
│ ├── templates/ # HTML templates
│ ├── static/ # CSS/JS files
│ └── admin.py
├── utils.py # Twilio SMS function
└── templates/
└── base.html


---

## 🔄 Project Flow (Short Summary)

1. Customer places order  
2. Staff selects food items and enters mobile & table number  
3. Django creates Order and OrderItems  
4. Bill auto-calculates subtotal, GST, total  
5. Bill is shown on screen + sent via SMS (Twilio)  
6. Staff prints bill if needed  

---

## 📦 Features

- ✅ Add/update/delete menu items from Django Admin  
- ✅ Create order with food items, quantity, table number, and mobile  
- ✅ Auto calculate subtotal, GST (e.g., 5%), and total  
- ✅ Generate order summary and bill  
- ✅ Send bill via SMS using Twilio API  
- ✅ Print-ready invoice using HTML print  
- ✅ Stores order data for future analytics  

---

## 📲 API Flow (How SMS is Sent)

1. Order is created with food items and quantities.  
2. A formatted SMS string is prepared:
    ```
    Dragon Bowl Restaurant
    Order #101
    2 x Fried Rice - ₹200
    Total: ₹400
    Thank You! Visit Again
    ```
3. SMS is sent using:
```python
from twilio.rest import Client

client = Client("TWILIO_SID", "TWILIO_TOKEN")
client.messages.create(
    body=bill_text,
    from_='+1XXXXXXXXXX',  # Your Twilio number
    to=order.mobile_number
)

git clone https://github.com/YOUR_USERNAME/chinese-restaurant-billing-system.git
cd chinese-restaurant-billing-system
pip install -r requirements.txt

python manage.py makemigrations
python manage.py migrate
python manage.py runserver


