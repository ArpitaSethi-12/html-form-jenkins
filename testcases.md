# Test Cases - Student Registration Form

| Test ID | Test Scenario              | Test Data        | Expected Result                       |
| ------- | -------------------------- | ---------------- | ------------------------------------- |
| TC01    | Verify HTML file exists    | index.html       | File should exist                     |
| TC02    | Verify form exists         | registrationForm | Form should be present                |
| TC03    | Verify Name field          | id="name"        | Name input should exist               |
| TC04    | Verify Email field         | type="email"     | Email input should exist              |
| TC05    | Verify Contact field       | id="contact"     | Contact input should exist            |
| TC06    | Verify Submit button       | type="submit"    | Submit button should exist            |
| TC07    | Verify required validation | Empty form       | Browser should prevent submission     |
| TC08    | Verify email validation    | Invalid email    | Browser should reject invalid email   |
| TC09    | Verify contact validation  | 10-digit number  | Contact field should accept 10 digits |
| TC10    | Verify success message     | Valid form data  | Success message should appear         |
