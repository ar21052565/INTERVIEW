### **Maternal Harmony Project Overview**

The **Maternal Harmony** project aims to enhance transparency in the distribution of essential items (like soybean, clothes, medicine, wheat, etc.) provided by the government to pregnant women in rural villages. These items are sent to AASHA workers, who distribute them. Unfortunately, some AASHA workers fail to deliver the complete set of items, leading to a lack of transparency and awareness among the women.

The project’s goal is to ensure that pregnant women can verify the items they have received and report discrepancies, thereby ensuring accountability and transparency in the distribution process. The web application was designed to facilitate this by allowing women to log in, view the list of items, verify the ones they have received, and submit this information for transparency.

### **Key Features & Functionality**

---

#### **1. Frontend Technologies**

The frontend of the Maternal Harmony project is built using **HTML**, **CSS**, and **JavaScript**, which ensure a smooth user experience and interface for the pregnant women who will use the platform.

- **HTML (HyperText Markup Language)**:
  - HTML is the backbone of the web application, providing the structure and layout for the web pages. In this project, HTML is used to create forms for user registration, login, and item selection. These pages form the interface where users interact with the application.
  
- **CSS (Cascading Style Sheets)**:
  - CSS is used to style and make the HTML elements visually appealing. It allows for customization of the layout, fonts, colors, and other aesthetic aspects of the page. The CSS code ensures that the application is easy to navigate and looks visually appealing to the users.
  
- **JavaScript**:
  - JavaScript adds interactivity to the web pages. It handles client-side activities like form validation, sending AJAX requests to the server, and dynamically updating the page as users interact with it. For example, when a user selects the items they've received, JavaScript handles the data submission to the backend and updates the UI accordingly.

---

#### **2. Backend Technologies**

The backend of the application is responsible for processing data, managing user authentication, and interacting with the database. The backend is built using **Node.js** and **Express.js**.

- **Node.js**:
  - Node.js is a JavaScript runtime environment that allows the execution of JavaScript code on the server side. It is particularly useful for building scalable applications that need to handle many simultaneous connections. In this project, Node.js is used to handle requests from the frontend, process user data, manage authentication, and interact with the MongoDB database.
  
- **Express.js**:
  - Express.js is a web application framework that simplifies the process of building APIs and handling HTTP requests in Node.js. It provides helpful middleware to manage routing, authentication, and requests. In this project, Express.js handles user registration, login, OTP verification, and face recognition integration, as well as facilitating the data flow between the frontend and backend.

---

#### **3. Database Technology**

The project uses **MongoDB**, a NoSQL database, to store user data and other necessary information.

- **MongoDB**:
  - MongoDB is a non-relational, flexible database that stores data in a JSON-like format (BSON). MongoDB is ideal for applications that require dynamic and scalable data storage. It doesn't require a predefined schema, making it highly adaptable. In this project, MongoDB is used to store user registration information, login credentials (hashed using bcrypt), records of the items distributed, and health data used for machine learning predictions.
  
---

#### **4. Security Technologies**

Ensuring security in the application is vital, as it handles sensitive data like personal information and health-related details.

- **Bcrypt**:
  - Bcrypt is a password hashing function that ensures that users' passwords are stored securely. Instead of storing the password in plain text, Bcrypt hashes the password before storing it in the database. This ensures that even if the database is compromised, the passwords cannot be retrieved. Only the correct password can match the stored hash, adding a layer of security to protect user data.

---

#### **5. Authentication Methods**

The application uses multiple layers of authentication to ensure that only authorized users can access certain features.

- **OTP Verification**:
  - OTP (One-Time Password) is a common authentication technique where a unique code is sent to the user’s phone or email. This code is only valid for a short time, adding an additional layer of security to ensure that the person logging in is the actual user.

- **Gmail Verification**:
  - Gmail verification confirms that the user has access to the provided email address. When a user registers, they receive a verification email containing a link or code to confirm their identity and prevent fraudulent registrations.

- **Face Recognition**:
  - Face recognition is used as a biometric authentication method. This ensures that only the registered user can verify the items they have received. The face recognition system compares the uploaded image with the stored image and grants access to the items page once a match is confirmed.

---

#### **6. Machine Learning Model**

An **SVM (Support Vector Machine)** model is integrated into the application to predict potential health risks, such as diabetes or irregular heartbeats.

- **SVM (Support Vector Machine)**:
  - SVM is a supervised machine learning algorithm that is effective in classification tasks. In this project, the SVM model takes user health data (like age, weight, glucose levels, etc.) and classifies whether the user is at risk of diabetes or has irregular heartbeat conditions. SVM is preferred due to its ability to handle high-dimensional spaces and its robustness against overfitting, which is important when dealing with medical data.

---

#### **7. Item Verification and Submission**

Once the user logs in, they can verify the items they have received by ticking them off a list. 

- **Item Verification**:
  - After face recognition verification, the user is allowed to access the list of items meant for distribution. They can tick the items they have received.
  
- **Submission & Transparency**:
  - Once the user selects the items they have received, the data is submitted and automatically converted into an Excel sheet. This helps to maintain a transparent record of the distribution.
  - The Excel sheet is emailed to both the user and the distribution head using **Gmail**, ensuring transparency and accountability in the distribution process.

---

#### **8. Excel Sheet Generation**

To ensure there is a clear record of the items distributed, an Excel sheet is generated containing the data submitted by the user.

- **Excel Sheet Generation**:
  - The data submitted by the user regarding the items they have received is converted into an Excel sheet. This is done using a library like **xlsx** or **pandas** in Node.js.
  - The Excel sheet is then automatically emailed to both the user and the head of the distribution center. This helps ensure transparency and accountability in the distribution process.

---

### **Technology Stack Summary:**

- **Frontend**: HTML, CSS, JavaScript
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Security**: Bcrypt (Password Hashing)
- **Authentication**: OTP Verification, Gmail Verification, Face Recognition
- **Machine Learning**: SVM (Support Vector Machine)
- **Excel Sheet Generation**: Using Node.js libraries (e.g., xlsx or pandas)

---

### **Conclusion**

The **Maternal Harmony** project is designed to ensure transparency, security, and health awareness for pregnant women in rural villages. By integrating face recognition, OTP, and Gmail verification for secure authentication, and employing machine learning for health predictions, the project addresses key issues in item distribution and health management. The use of modern technologies like Node.js, Express.js, MongoDB, and SVM ensures that the application is both functional and scalable, providing a seamless user experience.
