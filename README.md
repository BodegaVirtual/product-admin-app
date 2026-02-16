# Product Admin Dashboard

A modern, responsive administrative interface for managing products, categories, and orders. This application serves as the frontend for the [GraphQL Product Service](https://github.com/BodegaVirtual/graphql-product-service), providing a user-friendly dashboard for inventory and order management.

---

## 🚀 Features

* **Inventory Management**: Full CRUD operations for products including SKU, pricing, and image management.
* **Category Hierarchy**: Manage product categories and system metadata.
* **Order Tracking**: Real-time view of customer orders and payment statuses.
* **GraphQL Integration**: Powered by Apollo Client for efficient data fetching and state management.
* **Secure Access**: Integrated with AWS Cognito via the backend for protected administrative routes.
* **Responsive Design**: Built with React and optimized for both desktop and mobile administration.

---

## 🛠 Tech Stack

* **Frontend**: React.js
* **Data Fetching**: Apollo Client (GraphQL)
* **Styling**: CSS / Tailwind CSS
* **Build Tool**: Vite
* **Authentication**: AWS Amplify / Cognito

---

## 📦 Getting Started

### Prerequisites

* **Node.js**: v18.x or higher
* **NPM/Yarn**: Latest stable version
* **Backend API**: A running instance of the [GraphQL Product Service](https://github.com/BodegaVirtual/graphql-product-service).

### Installation

1.  **Clone the repository**:
    ```bash
    git clone [https://github.com/BodegaVirtual/product-admin-app.git](https://github.com/BodegaVirtual/product-admin-app.git)
    cd product-admin-app
    ```

2.  **Install dependencies**:
    ```bash
    npm install
    ```

3.  **Configure Environment**:
    Create a `.env` file in the root directory and add your GraphQL endpoint and Cognito configuration:
    ```env
    VITE_GRAPHQL_URI=[https://your-api-endpoint.amazonaws.com/v1/admin/graphql](https://your-api-endpoint.amazonaws.com/v1/admin/graphql)
    VITE_COGNITO_USER_POOL_ID=your_user_pool_id
    VITE_COGNITO_CLIENT_ID=your_client_id
    VITE_COGNITO_REGION=us-east-2
    ```

4.  **Run Locally**:
    ```bash
    npm run dev
    ```

---

## 🚢 Deployment

To create an optimized production build:

1.  **Build your React app**:
```bash
npm run build
```
2.  **Sync files to S3**:
```bash
aws s3 sync dist/ s3://[Your-S3-Bucket] --delete
```
3.  **Create the CloudFront invalidation for all files**:
```bash
aws cloudfront create-invalidation --distribution-id [Your-Distribution-Identifier] --paths "/*"
```
---

## 📂 Project Structure

* **`src/components`**: Reusable UI elements (Buttons, Inputs, Tables).
* **`src/graphql`**: Queries and Mutations definitions.
* **`src/pages`**: Main view components (Dashboard, Product List, Order Details).
* **`src/context`**: React Context providers for Auth and App state.
* **`public/`**: Static assets and icons.

---

## 🌐 Demo Environments
Use the following credentials to test the live demo applications:

| Application | URL | User | Password |
| :--- | :--- | :--- | :--- |
| **Admin App** | https://admindemo.bolito.co/ | `test@test.co` | `Demo1234` |

---

## 📄 License

This project is licensed under the **Apache License 2.0**.

### Limitation of Liability
This software is provided "AS IS", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability or fitness for a particular purpose. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or the use or other dealings in the software.
