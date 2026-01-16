Login
#authentication/views.py


from django.shortcuts import render
from django.http import HttpResponse
# Create your views here.
def home(request):
    return render(request, "authentication/index.html")

def signup(request):    
    return render(request, "authentication/signup.html")

def signin(request):
    return render(request, "authentication/signin.html")

def signout(request):
    pass


#authentication/apps.py
from django.apps import AppConfig


class AuthenticatorConfig(AppConfig):
    default_auto_field = 'django.db.models.BigAutoField'
    name = 'authenticator'


#authentication/urls.py
from django.contrib import admin
from django.urls import path, include 
from .views import home
urlpatterns = [
    path('', home, name='home'),
    path('signup', views.signup, name='signup'),
    path('signin', views.signin, name='signin'),
    path('signout', views.signout, name='signout'),
]





