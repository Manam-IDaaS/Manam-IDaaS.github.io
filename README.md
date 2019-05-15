# manam.github.io
Manam is a IDaaS


# How use IDaaS API
**Register**
----
  This API use to register user

* **URL**

  /auth/register

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
 
   None

* **Data Params**

  **Required:**
  ```
  name=[string]
  email=[string]
  password=[string] 
  confirm_password=[string] 
  customer_token=[string]
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    ```
    {
    "location": "/",
    "message": "Please verify your account, an e-mail has been sent to you.",
    "status": "success"
    }
    ```
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
   

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/auth/register",
      dataType: "json",
      type : "POST",
      data: {name:"myname", email:"myemail@mail.com", password:"password", confirm_password:"password", "customer_token":"cus_token"}
      success : function(r) {
        console.log(r);
      }
    });
  ```



**Confirm**
----
  This API use to confirm user

* **URL**

  /auth/confirm

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**

    ```
    cnf=[string]
    customer_token=[string]
    ```

* **Data Params**

 None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    ```
    {
    "location": "/",
    "message": "You have successfully confirmed your account.",
    "status": "success"
    }
    ```
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
   

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/auth/confirm?cnf=FFL5QDOYTXJZcO3SdcDgd8Kv-_euyLqVwm-eFagHZG_KCBLgtyhUkjFAeeDXvMFVVame3vXKyiWbnpNAVxQI8A%3D%3D&amp;customer_token=cus_token",
      dataType: "json",
      type : "GET",
      success : function(r) {
        console.log(r);
      }
    });
  ```
  
  
**login**
----
  This API use to login user

* **URL**

  /auth/login

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
 
   None

* **Data Params**

  **Required:**
  ```
  email=[string]
  password=[string] 
  customer_token=[string]
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    ```
    {
    "location": "/",
    "status": "success"
    }
    ```
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
   

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/auth/login",
      dataType: "json",
      type : "POST",
      data: { email:"myemail@mail.com", password:"password", "customer_token":"cus_token"}
      success : function(r) {
        console.log(r);
      }
    });
  ```

  
**recover**
----
  This API use to recover user

* **URL**

  /auth/recover

* **Method:**

  `POST`
  
*  **URL Params**

   **Required:**
 
   None

* **Data Params**

  **Required:**
  ```
  email=[string] 
  customer_token=[string]
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** 
    ```
    {
    "location": "/",
    "message": "An email has been sent to you with further instructions on how to reset your password.",
    "status": "success"
    }
    ```
 
* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
   

* **Sample Call:**

  ```javascript
    $.ajax({
      url: "/auth/recover",
      dataType: "json",
      type : "POST",
      data: { email:"myemail@mail.com", "customer_token":"cus_token"}
      success : function(r) {
        console.log(r);
      }
    });
  ```

**Google Login (oauth2)**
----
use this link
`
 <a href="/googlelogin/[customer-token]">Google Log In</a>
 `
 
 Contact to admin for give customer-token



















