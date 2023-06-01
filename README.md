# django_shop

-> django-admin startproject myshop
-> cd myshop/
-> django-admin startapp shop
settings.py: add 'shop' to INSTALLED_APPS
models.py: class Category and Product
-> python manage.py makemigrations
-> python manage.py migrate
admin.py: class CategoryAdmin and ProductAdmin
-> python manage.py createsuperuser
add necessary goods through admin panel
view.py: def product_list and def product_detail
urls.py: add path in shop/urls.py and urls.py
models.py: add def get_absolute_url
templates: base.html, detail.html, list.html
settings.py: MEDIA_URL and MEDIA_ROOT
urls.py: add if settings.DEBUG
settings.py: CART_SESSION_ID
-> django-admin startapp cart
settings.py: add 'cart' to INSTALLED_APPS
cart.py: class Cart
forms.py: class CartAddProductForm
views.py: @require_POST def cart_add & def cart_remove & def cart_detail
urls.py: for cart
urls.py: add '^cart/' to main myshop
templates: detail.html
shop/views.py: edit def product_detail
detail.html: add class="price"
context_processors.py: def cart
settings.py: TEMPLATES - add 'cart.context_processors.cart'
shop/base.html: change div class="cart"
-> python manage.py startapp orders
settings.py: add 'orders' to INSTALLED_APPS
orders/models.py: class Order & class OrderItem
-> python manage.py makemigrations
-> python manage.py migrate
orders/admin.py: class
orders/forms.py: class OrderCreateForm
orders/views.py: def order_create
orders/urls.py: ^create/
myshop/urls.py: ^orders/
cart/detail.html: Checkout change
orders/templates: create.html & created.html