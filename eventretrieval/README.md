-> OVERVIEW:

1. The Event Retrieval Microservice is designed to fetch event data from an external provider and make it available through an API. It retrieves event information, including IDs, titles, start dates, end dates, and pricing details. The microservice allows users to specify a time range for which they want to retrieve events.

-> FEATURES:
1. Fetch events from an external provider.
2. Filter events based on a specified time range.
3. Include or exclude past events.
4. Cache fetched events to improve performance and reliability.

-> IMPLEMENTATION DETAILS

TECHNOLOGIES USED
1. Python
2. Django
3. Requests library for HTTP requests
4. ElementTree for XML parsing

CACHING STRATEGY
1. Implemented caching of fetched events using a global variable event_cache.
2. If the provider service is down, the microservice returns the cached events.
3. Cache is updated whenever new events are fetched successfully from the provider.

ERROR HANDLING
1. Handled various exceptions that may occur during fetching events or parsing XML data.
2. Logged error messages for debugging and monitoring.

PERFORMANCE OPTIMIZATION
1. Designed the microservice to maintain consistent performance regardless of the provider service status.
2. Cached events are used when the provider service is down to ensure uninterrupted functionality.

FUTURE ENHANCEMENTS
1. Implement a more sophisticated caching mechanism using a database or caching library for better scalability and performance.
2. Add support for more advanced filtering options, such as filtering by event type, location, or category.

-> USAGE
To use the Event Retrieval Microservice, follow these steps:
1. Ensure that Python and Django are installed on your system.
2. Clone the repository to your local machine.
3. Set up the required dependencies by running "pip install -r requirements.txt".
4. Run the Django server using "python manage.py runserver".
5. Access the API endpoints to fetch events based on your requirements.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/navinNinjatech/dataretrieval.git

2. Navigate to the project directory

   cd eventretrieval

3. Install the required dependencies:

   pip install -r requirements.txt

4. To start the Django server, run the following command:

   python manage.py runserver

### API ENDPOINTS
 -> Fetch Events: /search
 -> Method: GET

# Parameters:
 -> starts_at: The start date and time of the range.
 -> ends_at: The end date and time of the range.

# Sample Response
" 
 {
    "events": [
        {
            "id": "1",
            "title": "Sample Event",
            "start_date": "2024-04-01",
            "start_time": "09:00:00",
            "end_date": "2024-04-01",
            "end_time": "17:00:00",
            "min_price": 10.0,
            "max_price": 50.0
        },
        {
            "id": "2",
            "title": "Another Event",
            "start_date": "2024-04-15",
            "start_time": "10:00:00",
            "end_date": "2024-04-15",
            "end_time": "18:00:00",
            "min_price": 15.0,
            "max_price": 70.0
        }
    ]
}
 "

