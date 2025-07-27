# QR-Generator

## Overview

QR-Generator is a simple web application that allows users to generate QR codes for product IDs and prices. The project consists of a Node.js backend for QR code generation and a frontend client for user input and displaying the resulting QR code.

---

## Features

- **User Input:** Enter a product ID and price to generate a QR code.
- **Dynamic QR Generation:** Generates a QR code image containing the product information.
- **Downloadable QR Image:** The generated QR code can be downloaded directly from the browser.
- **Simple Web Interface:** Clean and minimal UI for quick and easy QR code creation.

---

## How It Works

1. The user fills out a form with a product `ID` and `Price` on the frontend.
2. On submission, the frontend sends this data to the backend server using a POST request.
3. The backend formats this information and generates a QR code image using the [`qrcode`](https://www.npmjs.com/package/qrcode) package.
4. The server responds with the QR code image, which is displayed on the page.

---

## Project Structure

```
QR-Generator/
├── Client/
│   ├── index.html      # Frontend HTML page
│   ├── script.js       # Handles form and image display logic
│   └── style.css       # Basic styling
└── Server/
    ├── app.js          # Express server setup
    ├── routes.js       # API route definition
    ├── controller.js   # Handles QR generation logic
    └── service.js      # Data formatting and QR code creation
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v12+ recommended)
- [npm](https://www.npmjs.com/)

### Backend Setup

1. Navigate to the `Server` directory:
    ```bash
    cd Server
    ```
2. Install dependencies:
    ```bash
    npm install
    ```
3. Start the server:
    ```bash
    node app.js
    ```
   The server will run on `http://localhost:3000`.

### Frontend Usage

1. Open `Client/index.html` in your web browser.
2. Enter a product ID and price.
3. Click "Generate QR Code" to view and download your QR image.

---

## API Endpoint

- **POST `/generate-qr`**
    - **Body:** `{ data: { id: string, price: string } }`
    - **Response:** Returns a PNG image of the generated QR code.

---

## Example

1. Enter `ID: 12345`, `Price: 99.99`
2. Click "Generate QR Code"
3. A QR code image appears, encoding:  
   `Product ID: 12345, Price: $99.99`

---

## Dependencies

- [Express](https://expressjs.com/)
- [body-parser](https://www.npmjs.com/package/body-parser)
- [cors](https://www.npmjs.com/package/cors)
- [qrcode](https://www.npmjs.com/package/qrcode)

---
