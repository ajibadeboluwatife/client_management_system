# client_management_system

Installation and Local Development
# client-Management-System

![Python Version](https://img.shields.io/badge/python-3.12-blue)
![CI](https://github.com/jibbs1703/LiBookTrac/actions/workflows/CI.yaml/badge.svg)
[![Pydantic v2](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/pydantic/pydantic/main/docs/badge/v2.json)](https://pydantic.dev)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-v16-blue?logo=postgresql&style=flat)](https://www.postgresql.org/)
![pre-commit](https://img.shields.io/badge/precommit-enabled-yellow)
![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)
![license](https://img.shields.io/github/license/peaceiris/actions-gh-pages.svg)

The **Vendor Management System** is a platform designed to streamline bookings and payments for hairdressers. Vendors provide their services, and users can easily book appointments, make payments, and manage their schedules—all in one place.

## Features
- **Vendor Registration & Management** – Hairdressers can set up profiles, list services, and manage availability.
- **User Bookings** – Customers can browse available services, schedule appointments, and receive booking confirmations.
- **Payment Integration** – Secure online payments via integrated payment gateways.
- **Appointment Tracking** – Users and vendors can view and manage upcoming appointments.
- **Notifications & Reminders** – Stay updated with automated reminders for bookings and payments.
- **Admin Dashboard** – Oversee platform activity, vendor performance, and user engagement.

## Installation and Local Development

1. Clone the repository:
```bash
   git clone https://github.com/yourusername/vendor-management-system.git
   cd vendor-management-system
```

2. Create and Activate Virual Environment for Bare Metal Development

```bash

python -m venv venv

venv\Scripts\activate

pip install -r backend/requirements.txt

```

3. Deactivate Virtual Environment

```bash

deactivate

```

4. Run Application Locally

```bash

uvicorn backend.v1.app.server.server:app --host 0.0.0.0 --port 8000 --reload

```

3. Build and Run Docker for Development

```bash
docker build -t vms-dev .

```

```bash
docker run -it --name vms-dev-container -v $(pwd):/workspace -p 8000:8000 vms-dev

```


```bash
docker exec -it vms-vms-db-1 bash
psql -U postgres
\l # List all databases
\l+ # List all databases with more details

\c vms # Connect to the vms database
\d # List all tables in the current database
\dt # List all tables in the current database with more details
\dn # List all schemas in the current database
SELECT * FROM client; # Run SQL query to check the client table

\q # Exit psql

# Run SQL query to check the client table
docker exec -it vms-vms-db-1 psql -U postgres -d vms -c "SELECT * FROM client;"
```

```bash
# Sample Client Login Credentials
{
  "first_name": "",
  "middle_name": "",
  "last_name": "",
  "email": "@",
  "username": "",
  "gender": "",
  "date_of_birth": "",
  "phone_number": "+",
  "address_1": "",
  "address_2": "",
  "city": "",
  "state": "",
  "zip_code": "",
  "country": "",
  "password": "",
  "confirm_password": ""
}
```

```bash
terraform init
terraform plan
terraform apply -auto-approve
```

```bash
# Running an Alembic Migration
alembic init migrations
alembic revision --autogenerate -m "Add user_id column to client table"

```

```bash
docker system prune -a
docker volume prune
docker network prune
docker container prune
```
