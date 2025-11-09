# ALX Travel App – ProDev Backend (Milestone 2)
### Project Overview
This repository contains the initial setup for the **ALX Travel App**, a real-world Django application that serves as the foundation for a travel listing platform. Milestone 2 focuses on on structuring relational data, serializing it for API endpoints, and programmatically populating the database with sample data to simulate real-world application scenarios..

## File Structure
```bash
.
├── README.md
└── alx_travel_app
    ├── README.md
    ├── alx_travel_app
    │   ├── __init__.py
    │   ├── asgi.py
    │   ├── settings.py          # Project configurations & database settings
    │   ├── urls.py              # URL routing
    │   └── wsgi.py
    ├── listings
    │   ├── __init__.py
    │   ├── admin.py             
    │   ├── apps.py
    │   ├── fixtures
    │   │   └── example.json     # Sample data for fixtures
    │   ├── management
    │   │   └── commands
    │   │       └── seed.py      # Seeder for populating sample data
    │   ├── migrations
    │   │   └── *.py             # Django migrations
    │   ├── models.py            # Listing, Booking, Review models
    │   ├── serializers.py       # DRF serializers
    │   ├── tests.py             
    │   └── views.py             # API viewsets
    ├── manage.py                # Django CLI entry point
    └── requirement.txt          # Python dependencies
```

## Quickstart
1. Create a virtual environment
    ```bash
    python -m venv venv
    source venv/bin/activate
    ```
2. Clone the repository
    ```bash
    git clone https://github.com/scottandee/alx_travel_app.git
    cd alx_travel_app/alx_travel_app/
    ```
3. Install dependencies
    ```bash
    pip install -r requirements.txt
    ```
4. Configure environment variables
    ```bash
    cp .env.example .env
    ```
5. Apply migrations
    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```
6. Run the development server
    ```bash
    python manage.py runserver
    ```
7. Access Swagger documentation
- Navigate to: http://127.0.0.1:8000/swagger/

## Models
Models define the database schema for the app. Located in listings/models.py:
- Listing – Represents travel listings such as hotels or apartments.
- Booking – Represents reservations linked to a `Listing` and `User`.
- Review – User reviews associated with a `Listing`.

## Serializers
Located in  `listings/serializers.py`, serializers handle conversion between model instances and JSON, and validate API inputs.

## Seeders
Seeders populate the database with sample data. Located in `listings/management/commands/seed.py`
Run the seeder with:
```bash
python manage.py seed
```
