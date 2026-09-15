 # 1. Research 
## 1.1 Table with Data Regarding Current Competition 
In the following table, I organized the current U.S. competitors, and based off various factors, determined whether they were direct or indirect competition.  

| Competitors | Competitor Type |Locate | Reserve | Pay | Pricing/Fee | Rating Average Apple Store | Rating Average Google Store | Number of Ratings Apple Store | Number of Ratings Google Store | Number of Users |   
|---|---|---|---|---|---|---|---|---|---|---|
| SpotHero | direct | yes | yes | yes | ~15-25% commission + service fee| 4.9/5 | 4.8/5 | 414,000 | 20,000 | not publicly disclosed | 
| Parkmobile | indirect | yes | yes | yes | ~$0.25-$0.50 per transaction| 4.8/5 | 4.3/5 | 1,400,000 | 88,000 | not publicly disclosed (largest US zone coverage)|  
| ParkWhiz | direct | yes | yes | yes | variable by city/facility | 4.8/5 | 4.2/5 | 188,000 | 27,400 | over 1 mil users historically reported |
| Passport Parking | indirect | yes | no | yes | ~$0.40 per transaction | 4.7/5 | 2.3/5 | 97,000 | 14,800 | Used across 800+ cities/operators|  
| Reef Technology Parking App | indirect | yes | no (session based not pre-booked) | yes | standard payment, no published fee | 2.1/5 | 2.3/5 | 2,800 | 9,100 | not publicly disclosed | 
| Parksy | indirect | yes | yes | yes | free for hosts; per-booking fee for drivers | 5 | n/a | 3 | n/a | not publicly disclosed |
| JustPark | direct | yes | yes | yes | small % service fee per booking | 4.8/5 | 3.5/5 | 29,000 | 22,000 | trusted by 10 mil drivers| 
| Park4Me | indirect| yes | yes | yes | no publishedfee | 2.2/5 | n/a | 98 | n/a | very limited - under 2000 downloads reported, app appears largely inactive/discontinued | 


# 2. Vision 
## 2.1 Business Requirements 
### *2.1.1 Background*
This project was acquired by us, $oftware Corp, a prominent software development studio because we couldn't help but notice how drivers often spend a significant amount of time searching for available parking, which in turn, leads to congestion, frustration, and overall, lost productivity. 

### *2.1.2 Business Oportunity*
Utilization is known as the percentage of a garage's total parking capacity that is actively occupied or reserved during a given time period. Across the competitive landscape, no major company currently solves the problem of underutilization for operators, most of them focus mostly on driver-facing search experience. This represents an opportunity to serve both sides of the market. We can help the drivers find and reserve parking in real time, while also giving operators the tools needed to fill capacity that they are currently losing revenue on. *(NOTE GREEN: make sure to expand and mention the explicit services will be providing -> real-time parking space availability, interactive map displaying available parking spots, [occupancy reporting and analytics], dynamic pricing, dynamic inventory management, [flexible booking and pricing], [frictionless access and navigation])*

### *2.1.3 Business Objectve*
The platform will provide drivers with real-time way to locate, reserve, and pay for parking, and will provide operators with tools to monitor occupancy, manage pricing, and improve overall utilization of their facilities. 

## 2.2 Vision of the Solution
### *2.2.1 Vision Statement*
For drivers who waste precious time searching for parking, __ is a mobile and web platform that allows them to locate, reserve, and pay for garage parking in real time. Unlike Passport Parking and Reef Technology, which require drivers to pay for a session after the fact, __ guarantees a reserved spot before arrival. Unlike SpotHero and ParkWhiz, which are built around rigid daily bookings, __ stands out by offering flexible micro-reservations suited to hourly, and shift-based parking needs. 

### *2.2.2 Scope*
This release will include driver-side search, reservation, and payment functionality, along with a real-time occupancy map, On the operator side, it will include tools to update availability and pricing in real time. 
# 3. Software Requirements Specification (SRS)
Project: Smart Parking Platform  
Version: 1.0  
Date: 09.10.2026

## 3.2 Overall Description  
- Users: Driver and Garage Operator
- System Environment: Web-based / mobile application
- Constraints: 
  - Budget: Unlimited 
  - Timeline: Fixed semester
  - Dependencies: on third-party services and APIs 
  - Must make sure to comply with all of following: 
    - Security and privacy requirements 
    - City and Ordinance 
    - Laws 
- Assumptions:  
  - Application has internet 
  - Internet access 

## 3.3 Functional Requirements
- FR1: The system shall allow user registration and authentication with email or phone number  
- FR2: The system shall allow the driver to see an interactive map displaying available parking locations 
- FR3: The system shall allow the driver reserve a parking spot 
- FR4: The system shall allow the driver to pay digitally 
- FR5: The system shall allow the parking operator to see the administrative dashboard
- FR6: The system shall allow the parking operator and driver access to reservation history and receipts *(DOUBLE CHECK IF FOR BOTH OR JUST PARKING OPERATOR)*
- FR7: The system shall allow the driver to receive notifications and alerts
- FR8: The system shall allow the parking operator to access occupancy reporting and analytics *(DOUBLE CHECK IF FOR BOTH OR JUST PARKING OPERATOR)*
- FR9: The system shall allow integration with external mapping/navigation services *(SEE IF WORD DIFFERENT / OR IN THIS SECTION SINCE NOT SURE)*

## 3.4 Non-Functional Requirements
- NFR1: The system shall load search results within 2-3 seconds of a query 
- NFR2: The system shall support concurrent access by at least 5,000 simultaneous users without degraded response time 
- NFR3: The system shall have all payment data encrypted and processed in compliance with PCI-DSS standards
- NFR4: The system shall store all user passwords utilizing industry-standard hashing
- NFR5: The system shall enforce session timeouts for users who have been inactive more than 5 minutes 
- NFR6: The system shall provide 99.99% uptime, with the exclusion of scheduled maintenance   
- NFR7: The system shall not lose reservation data in the event of a system failure (data persistence/backup) 

## 3.5 Use Cases 
*Use Case 1 | both*  
Title: Register an Account
Actor: Driver   
Precondition: User has downloaded the app or access the website; does not yet have an account  
Steps:  
1. User selects “Sign Up”   
2. User enters name, email, phone number, and password  
3. System validates input and creates the account 
4. System sends a verification email or code 
5. User verifies their account  

Postcondition: Account is created and active; user is logged in

*Use Case 2 | both*  
Title: Login   
Actor: Driver  
Precondition: User has an existing, verified account   
Steps:  
1. User enters email/username and password  
2. System validates credentials 
3. System grants access to the user’s account 

Postcondition: User is authenticated and lands on the home/search screen    

*Use Case 3 | mobile variant*  
Title: Search for available garages using current location   
Actor: Driver  
Precondition: User is logged in; app has location permission enabled on  the device  
Steps:  
1. User opens the app   
2. System automatically detects current GPS location 
3. Systems retrieves nearby garages with real-time availability and pricing, centered on the user’s current position
4. System displays results as a list and/or interactive map with live location marker 

Postcondition: Driver sees garages near their real-time physical location without manually entering an address 

*Use Case 4 | web version*  
Title: Search for available garages by entering destination  
Actor: Driver  
Precondition: User is logged via web browser; browser location permission is either unavailable, denied, or not requested  
Steps:  
1. User navigates to the site and lands on the search page   
2. User manually types in a destination address, landmark, or zip code 
3. System retrieves nearby garages with real-time availability and pricing based on the entered location 
4. System displays results as a list and/or embedded map 

Postcondition: Driver sees garages near their specified destination 

*Use Case 5 | both*  
Title: View garage details  
Actor: Driver  
Precondition: Driver has searched and received a list of nearby garages  
Steps:  
1. Driver selects a garage from the results  
2. System displays garage details: rate, address, hours, amenities, photos, and real-time availability count 
Postcondition: Driver has enough information to decide whether to reserve 

*Use Case 6 | both*  
Title: Reserve a parking spot  
Actor: Driver  
Precondition: Driver is viewing garage details; garage has available capacity   
Steps:  
1. Driver selects a reservation time window (arrival and departure time)  
2. Driver confirms the reservation and reviews the total estimated cost 
3. Driver submits payment information  
4. System processes payment authorization and confirms the reservation 

Postcondition: Spot is held for the driver’s time window; reservation confirmation is generated 

*Use Case 7 | mobile variant*  
Title: Confirm garage entry via QR code  
Actor: Driver  
Precondition: Driver has a confirmed reservation made via the website; has arrived at the garage entrance  
Steps:  
1. Driver opens the app and navigates to “My Reservations”   
2. Driver displays the QR code on their phone screen 
3. Garage entry scanner reads the QR code 
4. System verifies the reservation and opens the gate (or logs manual entry) 

Postcondition: Driver’s entry is logged; session start time is recorded 

*Use Case 8 | web variant*  
Title: Confirm garage entry via emailed/displayed code  
Actor: Driver  
Precondition: Driver has confirmed reservation made via the website; has arrived at the garage entrance  
Steps:  
1. Driver retrieves the entry code or barcode from the confirmation email or by logging into the website on their phone browser  
2. Driver shows the code to a garage attendant, or enters it manually at a keypad/kiosk if the garage lacks a scanner 
3. System verifies the reservation and logs entry 

Postcondition: Driver’s entry is logged; session start time is recorded 

*Use Case 9 | mobile variant*  
Title: Receive push notification  
Actor: Driver  
Precondition: Driver has the app installed with notification permissions enabled  
Steps:  
1. System triggers an event, like reservation confirmed, reservation expiring soon, payment processed
2. System sends a push notification directly to the driver’s device
3. Driver taps the notification to open the relevant screen in-app 

Postcondition: Driver is informed of time-sensitive updates in real time without needing to open the app manually 

*Use Case 10 | web variant*  
Title: Receive email/SMS notification   
Actor: Driver   
Precondition: Driver has an account with a verified email and/or phone number   
Steps:  
1. System triggers an event, like reservation confirmed, reservation expiring soon, payment processed
2. System sends an email and/or SMS to the driver’s registered contact info 
Postcondition: Driver is informed of updates, through with a slight delay compared to mobile push notifications 

*Use Case 11 | both*  
Title: Extend a reservation  
Actor: Driver  
Precondition: Driver has an active reservation; garage has continued availability past the original end time  
Steps:  
1. Driver navigates to “My Reservations” and selects the active reservation  
2. Driver selects “Extend” and chooses a new end time 
3. System checks continued availability and calculates the additional cost 
4. Driver confirms and system processes the additional payment 

Postcondition: Reservation end time is updated; driver’s spot remains held for the new duration
 

*Use Case 12 | both*  
Title: Cancel a reservation  
Actor: Driver   
Precondition: Driver has an active, unstarted reservation (has not yet entered the garage)  
Steps:  
1. Driver navigates to “My Reservations” and selects the reservation  
2. Driver selects “Cancel”  
3. System checks the garage’s cancellation policy and calculates any applicable refund  
4. System cancels the reservation and processes the refund, if eligible 

Postcondition: Reservation is canceled; spot is released back to available inventory; driver is notified of refund status 

*Use Case 13 | mobile variant*  
Title: Confirm garage exit and payment via app   
Actor: Driver   
Precondition: Driver has an active session (has entered the garage); is ready to leave
Steps:  
1. Driver approaches the exit; garage scanner reads the driver’s QR code, or the app auto-detects exit via Bluetooth beacon  
2. System calculates the final duration and charge 
3. System processes payment automatically through the driver’s saved payment method 
4. App sends an in-built receipt and confirmation 

Postcondition: Session is closed; driver is charged the correct amount; gate opens automatically 

*Use Case 14 | web variant*  
Title: Confirm garage exit and payment via manual checkout  
Actor: Driver   
Precondition: Driver has an active session (has entered the garage); is ready to leave  
Steps:  
1. Driver logs into the website (via phone browser) and selects “End Session” for their active reservation  
2. System calculates the final duration and charge 
3. System processes payment through the driver’s saved payment method on file 
4. System emails a receipt and confirmation 

Postcondition: Session is closed; driver is charged the correct amount; exit is authorized 

*Use Case 15 | both*  
Title: Log out   
Actor: Driver   
Precondition: User is logged in  
Steps:  
1. User selects “Log Out” from account settings  
2. System ends the active session 
Postcondition: User is returned to the login screen; session is closed 
