# JUMPINGMINDS.AI ASSIGNMENT

Elevator management system using Rest Apis

## Installation

1. Running locally
   - Clone the repository
   - Create a virtual environment
   - Activate the virtual environment and install the requirements
   - Run the server
   ```bash
    - git clone
    - cd elevator_system
    - python -m venv env
    - source env/bin/activate
    - pip install -r requirements.txt
    - python manage.py runserver
   ```

## Project Structure

```
.
├── README.md
├── elevator_system
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── api
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── migrations
│   ├── models
│   │   ├── __init__.py
│   │   ├── elevator.py
│   │   ├── elevator_request.py
│   │   └── elevator_system.py
│   ├── serializers
│   │   ├── __init__.py
│   │   ├── elevator_serializer.py
│   │   ├── elevator_request_serializer.py
│   │   └── elevator_system_serializer.py
│   ├── viewsets
│   │   ├── __init__.py
│   │   ├── elevator_request_viewset.py
│   │   ├── elevator_system_viewset.py
│   │   └── elevator_viewset.py
│   ├── tests.py
│   ├── urls.py
│   └── views.py
├── manage.py
├── requirements.txt
```

## Available APIs

1. Initialise the elevator system to create ‘n’ elevators in the system

   - Endpoint: `POST  /api/v1/elevator-systems/`
   - Request body:

   ```json
   {
     "system_name": "system1",
     "number_of_elevators": "3",
     "number_of_floors": "5"
   }
   ```

2. Get elevator system info
   - Endpoint: `GET  /api/v1/elevator-systems/<system-name>`
   - Lists all the elevators in the system and their current status
3. Create elevator request
   - Endpoint: `POST  /api/v1/elevator-systems/<system-id>/create-elevator-request`
   - Request body:
   ```json
   {
     "requested_from_floor": 5,
     "requested_to_floor": 3
   }
   ```
4. Get elevator requests

   - Endpoint: `GET  /api/v1/elevator-systems/<system-id>/elevators/<selevator-id>/requests/`
   - Lists all the requests made to the elevator

5. Get elevator request

   - Endpoint: `GET  /api/v1/elevator-systems/<system-id>/elevators/<elevator-id>/status/`
   - Responds with the current status of the elevator, current_floor, direction, next_stop, etc.

6. Update elevator info
   - Endpoint: `PATCH  /api/v1/elevator-systems/2/elevators/3/`
   - Request body:
   ```json
   {
     "id": 3,
     "elevator_number": 1,
     "current_floor": 1,
     "is_door_open": false,
     "direction": -1,
     "is_operational": false,
     "elevator_system": 2
   }
   ```
