# API Explorer: Mastering RESTful Connections

## API Overview

The MoviesDatabase API provides access to a wide range of movie data, including titles, genres, release years, and detailed information for each film. It supports filtering by year and genre, as well as pagination for efficient data retrieval. Authentication is handled via API keys, ensuring secure access. The API is designed for reliability, with clear error responses and support for scalable, real-time movie discovery applications.

## Version

Current API Version: v1

## Available Endpoints

- **/titles**  
   Retrieve a list of movies. Supports filtering by year, genre, and pagination.

- **/titles/{id}**  
   Get detailed information about a specific movie by its unique ID.

- **/titles/search/title/{title}**  
   Search for movies by title keyword.

- **/titles/utils/genres**  
   Fetch a list of all available movie genres.

- **/titles/utils/languages**  
   Retrieve supported languages for movie data.

- **/titles/utils/countries**  
   Get a list of countries associated with movies.

- **/titles/random**  
   Fetch a random movie from the database.

## Request and Response Format

### Request Example

To fetch a list of movies filtered by year and genre, send a GET request to the `/titles` endpoint with query parameters:

```
GET /titles?year=2023&genre=Action&page=1
Headers:
    Authorization: Bearer YOUR_API_KEY
```

### Response Example

A successful response returns a JSON object containing movie data and pagination info:

```json
{
  "results": [
    {
      "id": "tt1234567",
      "title": "Action Movie",
      "year": 2023,
      "genres": ["Action", "Adventure"],
      "language": "English",
      "country": "USA",
      "summary": "An action-packed adventure.",
      "posterUrl": "https://example.com/poster.jpg"
    }
    // ...more movies
  ],
  "page": 1,
  "totalPages": 10,
  "totalResults": 100
}
```

### Error Response Example

If an invalid API key is provided, the API returns an error object:

```json
{
  "error": "Unauthorized",
  "message": "Invalid API key provided.",
  "status": 401
}
```

## Authentication

To access the MoviesDatabase API, you must include a valid API key in the `Authorization` header of each request. The API key should be provided as a Bearer token. Example:

```
Authorization: Bearer YOUR_API_KEY
```

Requests without a valid API key will receive a `401 Unauthorized` error. Always keep your API key secure and never expose it in client-side code. For best security, store your API key in environment variables and use server-side API routes to proxy requests.

## Error Handling

When working with the MoviesDatabase API, you may encounter various error responses. Common errors include:

- **401 Unauthorized**: Returned when the API key is missing or invalid.  
   _Handling_: Check that the `Authorization` header contains a valid API key. Prompt users to re-authenticate or display an error message.

- **400 Bad Request**: Indicates invalid query parameters or malformed requests.  
   _Handling_: Validate all request parameters before sending. Display user-friendly messages for invalid input.

- **404 Not Found**: The requested resource does not exist.  
   _Handling_: Show a "Not Found" message or fallback UI if a movie or endpoint is unavailable.

- **429 Too Many Requests**: Triggered when exceeding API rate limits.  
   _Handling_: Implement request throttling or exponential backoff. Inform users to try again later.

- **500 Internal Server Error**: Server-side issues.  
   _Handling_: Display a generic error message and optionally log the error for debugging.

**Best Practices:**

- Use `try/catch` blocks in API calls to capture and handle errors gracefully.
- Check response status codes and display appropriate feedback.
- Implement loading and error states in your UI components.
- Use type guards to ensure API data integrity before rendering.

Example error handling in TypeScript:

```ts
try {
  const res = await fetch("/api/fetch-movies");
  if (!res.ok) {
    throw new Error(`Error: ${res.status}`);
  }
  const data = await res.json();
  // process data
} catch (error) {
  // Display error message to user
}
```

## Usage Limits and Best Practices

### Usage Limitations

- **Rate Limits:** The MoviesDatabase API enforces rate limits to ensure fair usage and system stability. Exceeding these limits will result in a `429 Too Many Requests` error. Refer to the API provider's documentation for specific rate thresholds.
- **Request Size:** Large queries or excessive pagination may be restricted. Use pagination parameters to limit the number of results per request.
- **Authentication:** Each request must include a valid API key. Unauthorized or excessive requests may lead to temporary suspension of access.

### Recommendations

- **Efficient Pagination:** Always use pagination to avoid large payloads and reduce server load.
- **Error Handling:** Implement robust error handling for rate limits and other common errors. Use exponential backoff or retry strategies when encountering `429` errors.
- **Caching:** Cache frequent or repeated requests on the client or server to minimize redundant API calls and improve performance.
- **Environment Variables:** Store API keys securely in environment variables and never expose them in client-side code.
- **Monitoring:** Track API usage and error rates to proactively address issues and stay within usage limits.
- **Documentation:** Regularly review API documentation for updates on limits, endpoints, and best practices.

By following these guidelines, you can ensure reliable, secure, and efficient integration with the MoviesDatabase API.
