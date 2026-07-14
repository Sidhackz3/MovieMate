## 📊 System Workflow

```mermaid
flowchart TD

A[User Opens MovieMania] --> B{Authenticated?}

B -->|No| C[Register / Login]
C --> D[JWT Authentication]
D --> E[Home Page]

B -->|Yes| E

E --> F[Browse Movies]
F --> G[Search / Filter Movies]
G --> H[View Movie Details]

H --> I[Select Date & Showtime]
I --> J[Choose Seats]

J --> K[Create Booking]

K --> L[Booking Stored in MongoDB]

L --> M[Payment]
M --> N[Booking Confirmation]

N --> O[Booking History]
```


## 🏗 Backend Architecture

```mermaid
flowchart LR

A[React Frontend]

A --> B[Express API]

B --> C[JWT Authentication Middleware]

C --> D[Controllers]

D --> E[MongoDB]

D --> F[TMDB API]

E --> G[Movies]
E --> H[Users]
E --> I[Bookings]
E --> J[Showtimes]
```

## 🔐 Authentication Flow

```mermaid
flowchart TD

A[User Login]

A --> B[POST /api/auth/login]

B --> C[Validate Credentials]

C -->|Valid| D[Generate JWT Token]

D --> E[Return Token]

E --> F[Store in LocalStorage]

F --> G[Protected API Requests]

G --> H[JWT Middleware]

H -->|Authorized| I[Controller]

H -->|Unauthorized| J[401 Unauthorized]
```



## 🎬 Movie Booking Workflow

```mermaid
flowchart TD

A[Browse Movies]

A --> B[Movie Details]

B --> C[Choose Date]

C --> D[Choose Showtime]

D --> E[Select Seats]

E --> F[Login Required]

F --> G[Create Booking]

G --> H[Save Booking]

H --> I[Payment]

I --> J[Confirm Booking]

J --> K[Booking Successful]
```

## 👨‍💼 Admin Workflow

```mermaid
flowchart TD

A[Admin Login]

A --> B[JWT Authentication]

B --> C{Role = Admin?}

C -->|No| D[Access Denied]

C -->|Yes| E[Admin Dashboard]

E --> F[Manage Movies]

E --> G[Manage Showtimes]

F --> H[Add Movie]

F --> I[Update Movie]

F --> J[Delete Movie]

G --> K[Create Showtime]

G --> L[Update Showtime]

G --> M[Delete Showtime]

H --> DB[(MongoDB)]

I --> DB

J --> DB

K --> DB

L --> DB

M --> DB
```

## 📂 Project Structure

```text
MovieMania
│
├── backend
│   ├── config
│   ├── controllers
│   ├── middleware
│   ├── models
│   ├── routes
│   ├── server.js
│   └── package.json
│
├── public
│
├── src
│   ├── assets
│   ├── components
│   ├── contexts
│   ├── hooks
│   ├── pages
│   ├── utils
│   ├── App.jsx
│   └── main.jsx
│
├── .env
├── package.json
└── README.md
```


## ☁️ Deployment Architecture

```mermaid
flowchart LR

A[User Browser]

A --> B[Vercel]

B --> C[Render Backend]

C --> D[MongoDB Atlas]

C --> E[TMDB API]
```


