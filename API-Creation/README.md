# 🌐 User Data API Server

This project implements a simple HTTP API server using Python's `http.server` module to handle various query requests against a static dataset of random user information (`json_rand_users_5000.json`). It covers basic connectivity, data aggregation, filtering with multiple parameters, and security/error handling.

## 👥 Authors
* **Yihang Zhu**
* **Pablo Cano Turnes**
* **Aleksandr Veretelnik**
* **Miguel Rodríguez Losada**

---

## 🛠️ Setup and Execution

### 🚀 Prerequisites
* **Python 3.x**
* **`requests`** library (for the client side)
* **`pandas`** library (for the client side to display DataFrames, though the server itself does not require it)
* The data file **`json_rand_users_5000.json`** must be in the same directory as the server script.
* The security file **`file_access_token_M7.csv`** must also be present.

### 🏃 Running the Server

The server runs locally on port 8080.

# python server_code.py
The server will start and listen at http://localhost:8080.
🗃️ Data Source
The server uses the USERS_DB variable, which is loaded from json_rand_users_5000.json. This dataset contains a list of random user profiles, including nationality (nat), gender, date of birth (dob), and contact information.

## ✨ API Endpoints (Milestones)
The server implements seven milestones, testing different aspects of API design, data querying, and access control.

# M1: Connectivity Test
Endpoint: /test_connectivity_M1

Functionality: Basic check to confirm the server is running and accessible.

Response: {"results": [{"Connectivity": "OK"}]} (HTTP 200)

# M2: Country Counts
Endpoint: /count_countries_M2

Functionality: Calculates the total number of users for each country (nat field) in the dataset.

Sorting: Results are sorted primarily by descending count and secondarily by ascending country code.

Response: A JSON list of objects containing country and count.

# M3: Filtered Country Counts
Endpoint: /count_countries_M3?countries=DK,ES,GB,IE,IR,NO,NL,NZ

Functionality: Extends M2 by allowing filtering based on the countries query parameter. Only counts for the specified country codes are returned.

Default: If countries is not provided, it behaves identically to M2.

# M4: Age Groups
Endpoint: /age_groups_M4

Functionality: Categorizes all users into predefined age groups based on dob.age.

Groups: <18, 18-29, 30-49, 50-64, >64.

Response: A JSON object with a single result entry listing the count for each group (e.g., age_<18, age_18_29, etc.).

# M5: Filtered Users
Endpoint: /users_M5?countries=...&gender=...&month=...&age=...

Functionality: Retrieves a list of users matching any combination of up to four query filters:

countries (based on nat)

gender

month (based on month of birth string "01".."12")

age (18-99 range)

Logic: A user must satisfy all provided filters to be included. If a filter is absent, it is ignored.

Response: A JSON list of all matching users, including their name_first, name_last, gender, age, country, postcode, and email.

# M6: Filtered Users with Error Control
Endpoint: /users_control_error_M6?countries=...&gender=...

Functionality: Extends M5 by implementing comprehensive format validation and error reporting for all query parameters.

Validation Checks:

Invalid Country IDs

Invalid Genders

Invalid Months

Invalid Ages

Invalid Fields (unsupported query parameters)

Response Logic:

Success: If no errors are found, it returns the filtered user list (like M5) with HTTP 200.

Failure: If any error is found, it aggregates all detected errors into a structured JSON and returns HTTP 400 (Bad Request).

# M7: Access Token Check
Endpoint: /access_token_M7?user_ID=...&access_token=...&countries=...

Functionality: Implements an access control layer that is mandatory before running the user filters (M5/M6 logic).

Authentication Check:

Verify that user_ID and access_token fields are present.

Verify that user_ID exists in the external security database (file_access_token_M7.csv).

Verify that the provided access_token matches the one stored for the user_ID.

Response Logic:

Authentication Error: Returns a specific error message (e.g., missing field, user not found, token mismatch) with HTTP 400.

Success: If authentication passes, it proceeds to filter users based on the other parameters (countries, gender, month, age) and returns the list with HTTP 200 (behaving like M5).