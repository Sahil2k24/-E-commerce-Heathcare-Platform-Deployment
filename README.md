# E-Commerce Healthcare Platform Deployment

## Overview

This project showcases the deployment of an advanced **E-Commerce Healthcare Platform**, designed to provide a seamless user experience, offering holistic healthcare products and personalized wellness solutions. The platform features a sophisticated technology stack and is hosted on **Hostinger VPS** to ensure high performance and scalability.

### Technologies Used
- **Frontend (Client-side)**: React
- **Frontend (Admin Panel)**: Next.js
- **Backend**: PHP Laravel
- **Process Management**: PM2
- **CI/CD**: Jenkins
- **Database**: MySQL
- **Hosting**: Hostinger VPS
- **Security**: SSL Certificates
- **DNS Management**: Hostinger DNS

---

## Features

- **Client-side Frontend**: Built with **React**, the client-side interface is responsive, providing users with a smooth, interactive experience for browsing products, making purchases, and managing their accounts.
  
- **Admin Panel**: Developed with **Next.js**, the admin panel provides an efficient system for managing product listings, orders, users, and other essential administrative tasks.

- **Backend**: Powered by **PHP Laravel**, the backend ensures robust, scalable, and secure server-side handling of data, transactions, and authentication.

- **Process Management**: **PM2** is utilized to manage and optimize the application processes, ensuring efficient scaling and smooth operation of the platform.

- **CI/CD Pipeline**: Jenkins is used to automate testing, building, and deployment of the platform. This CI/CD setup ensures reliable updates and fixes, minimizing downtime.

- **Personalized Wellness and Healthcare**: The platform integrates principles of **personalized wellness**, offering holistic products and services aimed at enhancing well-being.

- **Cruelty-Free Practices**: Committed to cruelty-free practices, the platform ensures that the products sold align with ethical and sustainable values.

---

## Deployment

### Hostinger VPS
The platform is hosted on **Hostinger VPS**, providing a reliable and scalable environment for the application to run smoothly.

### Frontend (Client-side) - React
The client-side is built with **React** to create a dynamic and responsive user interface, ensuring a seamless browsing experience for customers.

### Admin Panel - Next.js
The **Next.js** admin panel provides an efficient management system, enabling admins to easily manage products, orders, users, and other important aspects of the platform.

### Backend - PHP Laravel
The **PHP Laravel** backend handles all server-side functionalities, including database management, user authentication, and transaction processing. Laravel ensures the application is secure, scalable, and maintainable.

### Process Management - PM2
**PM2** is used to manage the application processes and services. It ensures the platform remains performant by enabling automatic restarts, monitoring, and scaling.

### CI/CD Pipeline with Jenkins
To maintain a smooth development workflow, **Jenkins** is set up to automate the **CI/CD** pipeline. This pipeline runs tests, builds the application, and deploys it automatically to the server whenever there are changes in the codebase.

---

## Features and Benefits

- **Holistic E-Commerce Experience**: The platform integrates personalized wellness with modern e-commerce, offering products aimed at enhancing users' overall health and well-being.
  
- **Scalable Architecture**: The application is designed to scale efficiently with a robust backend (PHP Laravel), a dynamic frontend (React), and automated process management (PM2).

- **Streamlined Admin Management**: Admins can easily manage the platform with the **Next.js** admin panel, offering a smooth workflow for adding products, managing customers, and tracking orders.

- **Real-Time Monitoring and Performance**: Using **PM2** and Jenkins, the platform ensures high availability and smooth performance, with real-time monitoring and automatic scaling when necessary.

- **Security**: The use of **SSL certificates** ensures encrypted communication, safeguarding sensitive user data. Additionally, security protocols are implemented to protect against potential vulnerabilities.

---

## Setup Instructions

To set up the platform locally or for further modifications, follow the steps below:

### Prerequisites

- **Node.js**: Required for React and Next.js.
- **PHP & Composer**: Required for the Laravel backend.
- **MySQL**: For the database.
- **PM2**: For process management.
- **Jenkins**: For CI/CD setup.

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/ecommerce-healthcare-platform.git
cd ecommerce-healthcare-platform
```

### 2. Install Dependencies

#### For Frontend (React & Next.js)
```bash
cd frontend
npm install
```

#### For Backend (PHP Laravel)
```bash
cd backend
composer install
```

#### For Process Management (PM2)
```bash
npm install -g pm2
```

### 3. Set Up MySQL Database

Ensure MySQL is installed and running, then create the necessary database and user.

```sql
CREATE DATABASE ecommerce_platform;
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON ecommerce_platform.* TO 'username'@'localhost';
```

Update the `.env` file in the backend directory with the correct database credentials.

### 4. Run Migrations and Seeders

Run Laravel migrations and seeders to set up the database schema and sample data.

```bash
php artisan migrate --seed
```

### 5. Start the Application

#### Start the Frontend (React)
```bash
cd frontend
npm start
```

#### Start the Admin Panel (Next.js)
```bash
cd admin
npm run dev
```

#### Start the Backend (Laravel)
```bash
cd backend
php artisan serve
```

### 6. Process Management with PM2

Run the application in the background using PM2 to ensure it stays alive and can scale as needed.

```bash
pm2 start backend/server.js
pm2 start frontend/server.js
pm2 start admin/server.js
```

---

## Continuous Integration & Deployment (CI/CD)

### Jenkins Setup

1. Install Jenkins and necessary plugins (Git, NodeJS, PHP, etc.).
2. Create a new pipeline job in Jenkins.
3. Configure the pipeline script to pull from the GitHub repository and run tests, build, and deploy commands.
4. Set up webhooks for automatic deployment when code changes are pushed to GitHub.

### Example Jenkinsfile

```groovy
pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/yourusername/ecommerce-healthcare-platform.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install' // React and Next.js
                sh 'composer install' // PHP Laravel
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test' // Run React tests
                sh 'php artisan test' // Run Laravel tests
            }
        }

        stage('Build & Deploy') {
            steps {
                sh 'npm run build' // Build React and Next.js apps
                sh 'php artisan migrate' // Run migrations
                sh 'pm2 restart all' // Restart PM2 processes
            }
        }
    }

    post {
        success {
            mail to: 'youremail@example.com', subject: 'Build Successful', body: 'The build and deployment were successful.'
        }
        failure {
            mail to: 'youremail@example.com', subject: 'Build Failed', body: 'The build or deployment failed. Please check Jenkins logs.'
        }
    }
}
```

---

## Conclusion

This **E-Commerce Healthcare Platform** offers a robust and scalable solution for businesses looking to enhance their online presence with a focus on holistic healthcare. By using a modern tech stack, integrating CI/CD automation, and utilizing process management tools like PM2, this platform is optimized for performance, security, and seamless user experiences.

For any issues, feel free to open an issue on the [GitHub repository](https://github.com/yourusername/ecommerce-healthcare-platform).

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
