# <PBX-Bank-Q-Manager>

## Description

Q Manager was built for PBX Bank to solve optimise the bank operations. With an efficient Queue management system in place, the bank can proactively manage and serve their customers with minimal time and effort.
This system uses an HTML and javascript for front-end coupled with Nod.js for backend.
Information is exchanged and processed using API services.

The system currently caters to the:
1. Customers trying to book an appointment at the bank either through the website or walk-in kiosks
2. Bank staff for viewing and controlling the Queue
3. Customer Relationship Officer for viewing details to attend to the customers

## Installation

Pre-requisiste software:
1. Visual Studio

Follow the below steps to run the PBX Bank Q Manager:
1. Download the folder AN6007_Group 10_Project Final Submission
2. Open Visual Studio 
3. Open the folder AN6007_Group 10_Project Final Submission
4. Open new terminal from the menu bar of Visual Studio
5. Issue the command 'npm init', press enter to all options
6. Issue the command 'npm install express'
7. Issue the command 'npm install path'
8. Issue the command 'npm install nodemon'
9. Issue the command 'npm install nodemailer'
10. Issue the command 'npm install cors'
11. Issue the command 'npm install body-parser'
12. Issue the command 'npm install ejs'
13. Modify package.json file: Scripts”: { "dev": "nodemon server.js"}
14. Activate the server with 'npm run devStart'
15. Ensure connect to the internet
16. Use FireFox browser to view the webpage


## Usage

Follow the below instructions to navigate through the system:
For Customer
1. For online registration, open your browser 'FireFox' and type the URL: 'http://localhost:9000/onlineBooking
2. Fill in all the user input fields and click on the button 'SUBMIT'.
3. View the acknowledgement message on the screen and wait for the confirmation email with details.
4. For walk-in registration, open your browser 'FireFox' and type the URL: 'http://localhost:9000/walk_in/Jurong' or 'http://localhost:9000/walk_in/Orchard' depend on the branch where the customer is located.
5. Fill in user input and click on the button 'SUBMIT'.
6. View the acknowledgement message on the screen.

For Display Screen
1. Open the browser 'FireFox' and type the URL: 'http://localhost:9000/display/Orchard'
2. View the current queue number that each counter is serving, the current waiting list, and the current missing list for the Orchard brand.
3. Open the browser 'FireFox' and type the URL: 'http://localhost:9000/display/Jurong'
4. View the current queue number that each counter is serving, the current waiting list, and the current missing list for the Jurong brand.
5. Open the browser 'FireFox' and type the URL: 'http://localhost:9000/sign_in/Orchard'
6. Fill in the queue number got online into the Orchard brand's check-in page and click on the button 'Submit'.
7. View the check-in result.
8. Open the browser 'FireFox' and type the URL: 'http://localhost:9000/sign_in/Jurong'
9. Fill in the queue number got online into the Jurong brand's check-in page and click on the button 'Submit'.
10. View the check-in result.

For Counter Officier
1. Open the browser 'FireFox' and type the URL: 'http://localhost:9000/selectcounter'.
2. Select branch and counter.
3. Press "Initialize" button to initiate the counter service.
4. Press "Call" button to call a customer to the particular counter.
5. Press "Clear" button when the service for the customer is done.
6. Press "Hold" button when the customer did not show up to the counter.
7. Press "Suspend Service" button to terminate the service for the particular counter.
8. View the Summary Table for the counter's service history, which includes status, start and end times, and service duration.

For Customer Relationship Officer
1. Open the browser 'FireFox' and type the URL: 'http://localhost:9000/selectcro'.
2. Select branch.
3. Enter queue number to requeue no-show customer back to the queueing line.
4. View the number of clients waiting in each customer category.
5. Press the "Stop" button to temporarily stop the receipt of a certain customer category.
6. Press the "Re-initiate" button to reinitiate the receipt of the certain customer category.
7. Select a category to view the waiting list in line.


## License

MIT License

Copyright (c) [2023] [MSBA-Team10]

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

---

The previous sections are the bare minimum, and your project will ultimately determine the content of this document. You might also want to consider adding the following sections.

## Features

The system is capable of:
1. Generating and issuing appointment numbers to the customers
2. Triggering an email with queue number to the customers upon successful registration
3. Displaying the queue status
4. Initiating and suspanding counter service
5. Calling and clearing customer queue number 
6. On hold missing cutomer queue number
7. Requeuing customer back to the waiting line
8. Controlling the queue receipt for each customer category
9. Viewing the current amount and in line waiting list for each customer category

## Tests

1. Test cases for customer registration - online appointment
   Expected Output: Irrespective of the queue number, customers will be called out on the basis of the below priority:
   Diamond > Gold > Silver > Normal
(i) User category - Diamond 
    Steps to reproduce: 
    (a) Open your browser 'FireFox' and type the URL: 'http://localhost:9000/onlineBooking
    (b) Fill phone number as '12345600'
    (c) Fill in the other required details
    (d) Click the 'SUBMIT' button
    (e) View the queue display

(ii) User category - Gold
    Steps to reproduce: 
    (a) Open your browser 'FireFox' and type the URL: 'http://localhost:9000/onlineBooking
    (b) Fill phone number as '12345601'
    (c) Fill in the other required details
    (d) Click the 'SUBMIT' button
    (e) View the queue display

(iii) User category - Silver
    Steps to reproduce: 
    (a) Open your browser 'FireFox' and type the URL: 'http://localhost:9000/onlineBooking
    (b) Fill phone number as '12345602'
    (c) Fill in the other required details
    (d) Click the 'SUBMIT' button
    (e) View the queue display

(iv) User category - Normal
    Steps to reproduce: 
    (a) Open your browser 'FireFox' and type the URL: 'http://localhost:9000/onlineBooking
    (b) Fill phone number as '12345609'
    (c) Fill in the other required details
    (d) Click the 'SUBMIT' button
    (e) View the queue display

2. Test cases for customer registration - walk in
   Expected Output: Irrespective of the queue number.
   Customers in walk-in pool will have lower priority compared with those made online reservation and arrive the branch on time. 
   Customers in walk-in pool will be called out on the basis of the below priority:
   Diamond > Gold > Silver > Normal 
(i) User category - Diamond 
    Steps to reproduce: 
    (a) Open your browser 'FireFox' and type the URL: 'http://localhost:9000/walk_in/Jurong' or 'http://localhost:9000/walk_in/Orchard' depend on the branch where the customer is located
    (b) Fill phone number as '22345600'
    (c) Click the 'SUBMIT' button
    (d) View the queue display

(ii) User category - Gold
    Steps to reproduce: 
    (a) Open your browser 'FireFox' and type the URL: 'http://localhost:9000/walk_in/Jurong' or 'http://localhost:9000/walk_in/Orchard' depend on the branch where the customer is located
    (b) Fill phone number as '22345601'
    (c) Click the 'SUBMIT' button
    (d) View the queue display

(iii) User category - Silver
    Steps to reproduce: 
    (a) Open your browser 'FireFox' and type the URL: 'http://localhost:9000/walk_in/Jurong' or 'http://localhost:9000/walk_in/Orchard' depend on the branch where the customer is located
    (b) Fill phone number as '22345602'
    (c) Click the 'SUBMIT' button
    (d) View the queue display

(iv) User category - Normal
    Steps to reproduce: 
    (a) Open your browser 'FireFox' and type the URL: 'http://localhost:9000/walk_in/Jurong' or 'http://localhost:9000/walk_in/Orchard' depend on the branch where the customer is located
    (b) Fill phone number as '22345609'
    (c) Click the 'SUBMIT' button
    (d) View the queue display

3. Test the result of check-in for the Orchard branch
i) Early check-in
(a) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/online booking 
(b) Select 'Orchard' for the Branch, choosing an appointment date and appointment slot that are later than the current time.
(c) Fill in your phone number and Email then click the button 'Submit'.
(d) View and remember the queue number shown on the page or email.
(e) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/sign_in/Orchard'.
(f) Enter the queue number you get in step (d) and click the button 'Submit'.
(g) The page should show this message: 'You are successfully check in but arrive early.Your slot is at [start time] to [end time] . We will let you get the service as soon as possible.'

ii) Check-in on time
(a) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/online booking 
(b) Select 'Orchard' for the Branch, choosing an appointment date and appointment slot that is the same as the current time.
(c) Fill in your phone number and Email then click the button 'Submit'.
(d) View and remember the queue number shown on the page or email.
(e) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/sign_in/Orchard'.
(f) Enter the queue number you get in step (d) and click the button 'Submit'.
(g) The page should show this message: 'You are successfully check in! Your slot is at [start time] to [end time]'

iii) Check-in late
(a) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/online booking 
(b) Select 'Orchard' for the Branch, choosing an appointment date and appointment slot that are earlier than the current time.
(c) Fill in your phone number and Email then click the button 'Submit'.
(d) View and remember the queue number shown on the page or email.
(e) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/sign_in/Orchard'.
(f) Enter the queue number you get in step (d) and click the button 'Submit'.
(g) The page should show this message: 'Sorry, you are late. Your slot is at [start time] to [end time]. Since your slot time is over, your priority will be the same as walk-in.'

iv) Check in without making a reservation in advance
(a) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/sign_in/Orchard'.
(b) Enter a queue number and click the button 'Submit'.
(g) The page should show this message: 'You didn't make a reservation.'

4. Test the result of check-in for the Jurong branch
i) Early check-in
(a) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/online booking 
(b) Select 'Jurong' for the Branch, choosing an appointment date and appointment slot that are later than the current time.
(c) Fill in your phone number and Email then click the button 'Submit'.
(d) View and remember the queue number shown on the page or email.
(e) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/sign_in/Jurong'.
(f) Enter the queue number you get in step (d) and click the button 'Submit'.
(g) The page should show this message: 'You are successfully check in but arrive early.Your slot is at [start time] to [end time] . We will let you get the service as soon as possible.'

ii) Check-in on time
(a) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/online booking 
(b) Select 'Jurong' for the Branch, choosing an appointment date and appointment slot that is the same as the current time.
(c) Fill in your phone number and Email then click the button 'Submit'.
(d) View and remember the queue number shown on the page or email.
(e) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/sign_in/Jurong'.
(f) Enter the queue number you get in step (d) and click the button 'Submit'.
(g) The page should show this message: 'You are successfully check in! Your slot is at [start time] to [end time]'

iii) Check-in late
(a) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/online booking 
(b) Select 'Jurong' for the Branch, choosing an appointment date and appointment slot that are earlier than the current time.
(c) Fill in your phone number and Email then click the button 'Submit'.
(d) View and remember the queue number shown on the page or email.
(e) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/sign_in/Jurong'.
(f) Enter the queue number you get in step (d) and click the button 'Submit'.
(g) The page should show this message: 'Sorry, you are late. Your slot is at [start time] to [end time]. Since your slot time is over, your priority will be the same as walk-in.'

iv) Check in without making a reservation in advance
(a) Open your browser 'FireFox' and type the URL: 'http:/localhost:9000/sign_in/Jurong'.
(b) Enter a queue number and click the button 'Submit'.
(g) The page should show this message: 'You didn't make a reservation.'