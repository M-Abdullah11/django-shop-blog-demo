# Django Shop & Blog Demo

A learning project built with **Python and Django** that combines a database-backed product catalog with a simple blog. The repository demonstrates Django's model–view–template (MVT) structure, URL routing, SQLite integration, server-rendered templates, and a Bootstrap-based storefront layout.

> **Status:** Educational prototype — not a production-ready e-commerce application. Some storefront routes are placeholders.

## Project Overview

The project has two Django applications:

- **Shop:** Reads product records from SQLite and displays product names, descriptions, and images in a card-based carousel. Includes an About page and Django admin integration for the `Product` model.
- **Blog:** Renders two template-based pages to demonstrate Django views and URL routing.

The store UI uses Bootstrap and includes visible **Add to Cart** buttons. Those buttons do **not** currently implement a working cart or order workflow.

## Tech Stack

| Area | Technology |
| --- | --- |
| Backend | Python, Django |
| Database | SQLite |
| Frontend | HTML, Django templates, Bootstrap, CSS |
| Media | Django media configuration and product image assets |
| Development tooling | Django management commands |

The source settings were generated with **Django 3.2.7**. This is an older Django release; use this version only for reproducing the educational project in a local environment, not for a new production deployment.

## Implemented Functionality

- Product data model with name, category, subcategory, price, description, date, and image fields.
- Product catalog page populated from `Product.objects.all()`.
- Bootstrap product cards and carousel-style presentation.
- Django admin registration for managing `Product` records.
- Store About page.
- Two blog pages rendered through Django routes and templates.
- Local static and media file configuration.

## Routes

| URL | Purpose | Current state |
| --- | --- | --- |
| `/admin/` | Django administration | Standard Django admin |
| `/shop/` | Product catalog | Implemented |
| `/shop/about/` | About page | Implemented |
| `/blog/` | Blog landing page | Implemented template |
| `/blog/boi/` | Secondary blog page | Implemented template |
| `/shop/contact/` | Contact | Placeholder response |
| `/shop/tracker/` | Order tracking | Placeholder response |
| `/shop/search/` | Product search | Placeholder response |
| `/shop/productview/` | Product detail | Placeholder response |
| `/shop/checkout/` | Checkout | Placeholder response |

## Repository Structure

```text
FOOL/                  # Django project configuration and root URLs
blog/                  # Blog views, URLs, templates, and static files
shop/                  # Product model, admin, views, URLs, and templates
media/shop/images/     # Product images in the repository
manage.py              # Django management command entry point
db.sqlite3             # Committed development database
```

## Run Locally

**Prerequisites:** Python, pip, and Git. A Python 3.8 virtual environment is suitable for reproducing this older project; it should not be treated as a modern production stack.

1. Clone the repository:

   ```bash
   git clone https://github.com/M-Abdullah11/django-shop-blog-demo.git
   cd django-shop-blog-demo
   ```

2. Create and activate a virtual environment:

   **Windows (PowerShell):**

   ```powershell
   py -3.8 -m venv .venv
   .\.venv\Scripts\Activate.ps1
   ```

   **macOS/Linux:**

   ```bash
   python3.8 -m venv .venv
   source .venv/bin/activate
   ```

3. Install the project's basic dependencies:

   ```bash
   python -m pip install "Django==3.2.7" Pillow
   ```

   The repository does not currently contain a `requirements.txt`, so this command documents the main packages needed by the inspected project. Additional changes may be needed for your environment.

4. Apply database migrations and start the development server:

   ```bash
   python manage.py migrate
   python manage.py runserver
   ```

5. Open the pages in your browser:

   - Shop: http://127.0.0.1:8000/shop/
   - Blog: http://127.0.0.1:8000/blog/
   - Admin: http://127.0.0.1:8000/admin/

   The repository includes a development SQLite database and sample image assets. You may need to create an admin user with `python manage.py createsuperuser` to log into Django admin.

**Note:** These setup steps are based on the checked-in source; the application was not executed or end-to-end tested as part of this documentation review.

## Screenshots

Screenshots of the running product catalog, blog, and admin interface can be added here after local verification. No demo screenshots are included in this README yet.

## Known Limitations & Possible Improvements

- Implement search, product details, cart state, checkout, and order tracking.
- Replace placeholder responses with real views and templates.
- Add tests, error handling, and clearer product validation.
- Add a maintained dependency file and update the Django version before production use.
- Clean development artifacts and review committed database contents.
- Move credentials and environment-specific settings out of tracked source code before any public deployment; rotate any credentials previously used in a deployed environment.

## Profile & Maintainer

**Muhammad Abdullah** — software development and technical project delivery.

- [GitHub](https://github.com/M-Abdullah11)
- [LinkedIn](https://www.linkedin.com/in/muhammad-abdullah-083906415/)

This repository is presented as an **educational Django prototype**, not a commercial store or a complete e-commerce system.
