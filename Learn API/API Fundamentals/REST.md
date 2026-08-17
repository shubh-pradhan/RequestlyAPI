## 1. Executive Summary

[[REST]] (Representational State Transfer) is an architectural style—a set of agreed-upon rules and conventions—for building APIs. If [[HTTP]] is the English language, REST is the grammatical rules for writing a formal business letter.

If you had two minutes before a meeting, know this: REST is the default way modern web applications talk to each other. It dictates that systems should communicate by exchanging data about "resources" (like users, orders, or products) using standard HTTP methods over the internet.

## 2. Why does this exist?

- **What problem was it created to solve?**
    
    In the early 2000s, computers talking to each other over the internet was chaotic. Companies needed a standardized, predictable, and scalable way for distributed systems to exchange data without needing complex software on both ends.
    
- **What existed before?**
    
    Heavyweight protocols like SOAP (Simple Object Access Protocol) and XML-RPC. They required massive, complex XML envelopes, strict contracts, and specialized software to parse the messages.
    
- **Why wasn't the previous approach sufficient?** SOAP was incredibly rigid and slow. It didn't utilize the built-in capabilities of the web (like caching). REST was created by Roy Fielding to leverage the existing architecture of the web ([[HTTP]]), making API integration lighter, faster, and radically simpler for a standard [[Backend Engineer]] to build.
    

## 3. Core Concepts

To speak fluently with engineers, you need to understand the fundamental constraints of a [[REST]] API:

- **Resources (Nouns):** In REST, everything is a resource, accessed via a URL. E.g., `[api.company.com/users](https://api.company.com/users)` represents the "users" resource.
    
- **Standard Methods (Verbs):** It uses standard [[HTTP]] methods to perform CRUD (Create, Read, Update, Delete) operations on those resources.
    
    - `POST` = Create
        
    - `GET` = Read
        
    - `PUT`/`PATCH` = Update
        
    - `DELETE` = Delete
        
- **Statelessness:** The server does not remember anything about the client between requests. Every single request must contain all the information (like [[Authentication]] tokens) necessary for the server to understand and process it.
    
- **Representations:** The server doesn't send the _actual_ database record; it sends a _representation_ of the state of that resource, almost always in JSON (JavaScript Object Notation) format today.
    

## 4. How does it work?

Let's look at a practical engineering workflow for fetching a user's profile:

1. **The Request:** The client (like a mobile app) wants user ID 123. It formats an [[HTTP]] `GET` request.
    
    - URL: `[https://api.myapp.com/users/123](https://api.myapp.com/users/123)`
        
    - Headers: Includes [[Authentication]] (e.g., Bearer token) and `Accept: application/json`.
        
2. **The Server:** The backend server receives the request. It checks if the token is valid, queries the database for user 123, and formats the data into a JSON object.
    
3. **The Response:** The server sends back a `200 OK` status code with the JSON payload (name, email, preferences) in the body.
    
4. **Stateless Follow-up:** If the client wants to update that user's name 5 seconds later, it must send a brand new `PUT` request with the authentication token all over again. The server hasn't "kept the line open."
    

## 5. Where is it used?

- **Company Size:** Universally used, from one-person indie projects to massive scale-outs at Netflix and Amazon.
    
- **Engineering Maturity:** Basic REST is simple, but mature engineering teams enforce strict [[REST]] guidelines (like proper status code usage, pagination, and versioning) and document them using [[OpenAPI]] specifications.
    
- **Common Use Cases:** Public APIs (like Stripe, Twilio, GitHub), mobile-to-backend communication, and connecting microservices within a company's internal infrastructure.
    

## 6. Who cares about this?

- **[[Backend Engineer]]:** They spend their days designing, building, and maintaining REST endpoints. This is core [[API Development]].
    
- **Frontend Engineers:** They consume these APIs and care deeply about how predictable and well-documented they are. Poorly designed REST APIs ruin [[Developer Collaboration]].
    
- **[[Enterprise Architecture]] / [[CTO]]:** They care about API standardization across the company. They don't want Team A building APIs one way and Team B building them completely differently.
    

## 7. Why do engineering teams adopt this?

- **Technical Reasons:** Statelessness makes it incredibly easy to scale. If you need to handle more traffic, you just add more servers behind a load balancer. Because each request is independent, any server can handle any request.
    
- **Business Reasons:** Ubiquity. If you publish a [[REST]] API, any developer in the world with basic programming skills knows how to interact with it, speeding up partner integrations.
    

## 8. Benefits

- **Decoupling:** The client and server are completely independent. A frontend can be rewritten from React to Angular without touching the backend, as long as the REST API contract remains the same.
    
- **Cacheability:** Because REST heavily utilizes standard [[HTTP]], responses to `GET` requests can be easily cached by browsers or CDNs, drastically reducing server load.
    
- **Tooling Ecosystem:** The massive popularity of REST means there are incredible tools for [[API Discovery]] (like Swagger), and [[API Testing]] (like [[Postman]], [[Bruno]], and [[Insomnia]]).
    

## 9. Drawbacks

- **Over-fetching:** A `GET /users/123` request might return 50 fields of data, but the mobile app only needed the user's first name. This wastes bandwidth.
    
- **Under-fetching (N+1 Problem):** If a client needs a user, their recent orders, and the product details of those orders, it might have to make 10 separate REST requests, slowing down the app.
    
- **Lack of Strict Contracts:** Unlike older protocols, REST itself doesn't technically enforce a strict schema, meaning a backend developer could accidentally break the frontend by renaming a JSON field unless guarded by strict [[Contract Testing]].
    

## 10. Common Misconceptions

- **"REST is a protocol."** False. HTTP is the protocol. REST is a set of design guidelines on _how_ to use HTTP.
    
- **"Our API is RESTful."** Most APIs are technically just "REST-ish." They use JSON and HTTP verbs, but break deeper REST constraints (like HATEOAS—using hyperlinks to guide the client through the API state). Most engineers don't care about absolute REST purity; they care about pragmatism.
    

## 11. Alternative Approaches

- **[[GraphQL]]:** Created by Facebook specifically to solve REST's over-fetching and under-fetching problems. The client requests exactly the fields it wants in a single query.
    
- **[[gRPC]]:** Created by Google. Uses Protocol Buffers instead of JSON. It is much faster and more efficient than REST, commonly used by [[Backend Teams]] for internal microservice-to-microservice communication where extreme speed is required.
    
- **[[Webhooks]]:** Used for event-driven architecture. Instead of the client constantly asking the server "Is it done yet?" via REST, the server pushes a message to the client when the event occurs.
    

## 12. Real-world Examples

- **Stripe API:** Widely considered the gold standard of a well-designed, highly pragmatic REST API. It uses clear resource URLs (`/v1/charges`), predictable verbs, and standardized error codes.
    
- **E-Commerce Cart:**
    
    - `POST /cart/items` (add a product)
        
    - `GET /cart` (view the cart)
        
    - `DELETE /cart/items/456` (remove a specific product)
        

## 13. Engineering Evolution

- **Startup:** A few developers build a quick Express.js or Django app with loose "REST-ish" endpoints. Documentation is an outdated wiki page or non-existent, making [[Onboarding]] hard.
    
- **Growth:** The team adopts [[OpenAPI]] to generate documentation and begins writing automated tests using [[REST Assured]] or [[Playwright]].
    
- **Enterprise:** The organization employs an API Gateway, enforces strict rate limiting, requires formal [[Contract Testing]] via CI/CD pipelines, and might begin migrating internal traffic to [[gRPC]] while keeping the public-facing API as REST.
    

## 14. Consultant Lens

- **Why should Technical Sales care?** You need to recognize when a customer is describing a REST API workflow versus a [[GraphQL]] or [[gRPC]] workflow, as tooling compatibility differs.
    
- **What this reveals about an organization:** If an [[Engineering Manager]] complains about [[Tool Sprawl]] between their documentation, testing, and debugging tools, they are struggling with the lifecycle management of their REST APIs.
    
- **[[When Requestly Fits]]:** REST APIs are the bread and butter of [[Requestly]].
    
    - **The Problem:** Frontend developers are frequently blocked waiting for backend developers to finish building new REST endpoints. QA engineers struggle to test edge cases (like a `500 Server Error` or a timeout) because they can't easily force the backend to fail. This causes friction in [[Environment Management]].
        
    - **The Requestly Solution:** Requestly is a master of [[Mocking]] REST APIs. A developer can intercept a REST request to a staging environment and modify the headers (to bypass [[Authentication]]), swap the URL to point to localhost, or inject a mock JSON response. This enables true [[Shift Left]] workflows, allowing UI development and [[API Testing]] to happen independently of backend readiness.
        

## 15. Key Takeaways

1. REST is the dominant architectural style for building web APIs, utilizing standard HTTP verbs (`GET`, `POST`, `PUT`, `DELETE`) and URLs.
    
2. Its stateless nature allows systems to scale easily, but can lead to inefficiencies like over-fetching data compared to newer technologies like [[GraphQL]].
    
3. Robust REST APIs require strong documentation (often via [[OpenAPI]]) and rigorous [[API Testing]] to ensure reliable contracts between frontend and backend.
    
4. Modifying and [[Mocking]] REST requests/responses is a critical workflow for debugging and parallel development, making it highly relevant for [[Requestly]] use cases.
    

## 16. Further Learning

- **Roy Fielding's Dissertation (Chapter 5):** The original academic paper that defined REST (for the ambitious reader).
    
- **Microsoft REST API Guidelines:** Excellent practical examples of how a massive enterprise structures their REST endpoints.
    
- **Swagger/OpenAPI Documentation:** To understand how modern teams document and enforce their REST contracts.