 # BidWave: Ride the Auction Tide

## Description
 Building an online marketplace where users can list items for sale in a timed auction format, with real-time bidding and notifications for participants. This project includes an admin dashboard for managing listings and bids

# Domain Object Model
## Domain Model for BidWave: Ride the Auction Tide

```mermaid
---
title : BidWave Ride the Auction Tide

---


classDiagram
    class User {
      +String userId
      +String username
      +String email
      +String password
      +Date registeredOn
      +login(email, password)
      +register(username, email, password)
      +updateProfile(details)
    }
    
    class Seller {
      +listAuction(productDetails)
      +updateAuction(auctionId, details)
    }
    class Buyer {
      +placeBid(auctionId, amount)
      +watchAuction(auctionId)
    }
    class Admin {
      +approveAuction(auctionId)
      +suspendUser(userId)
      +generateReports()
    }

    class Product {
      +String productId
      +String itemName
      +String description
      +String category
      +List~String~ images
      +updateProduct(details)
    }

    class Auction {
      +String auctionId
      +String productId
      +Float startPrice
      +Float currentPrice
      +Date startTime
      +Date endTime
      +String sellerId
      +String status
      +startAuction()
      +endAuction()
    }

    class Bid {
      +String bidId
      +String auctionId
      +String bidderId
      +Float amount
      +Date timePlaced
      +validateBid()
    }

    class Notification {
      +String notificationId
      +String userId
      +String message
      +String notificationType
      +Boolean seen
      +sendNotification()
      +markAsRead()
    }

    User <|-- Seller
    User <|-- Buyer
    User <|-- Admin
    Auction "1" --> "many" Bid : contains
    User "1" --> "many" Auction : lists
    User "1" --> "many" Bid : places
    User "1" --> "many" Notification : receives
    Product "1" --> "1" Auction : featured in


    

```
## How to Run the Project

Follow these steps to set up and run the project:

1. **Install frontend dependencies**:
   - Navigate to the frontend directory and install the required dependencies:
     ```bash
     npm install
     ```

2. **Run the frontend UI**:
   - Start the frontend development server:
     ```bash
     npm run dev
     ```
   - The frontend will be available at `http://localhost:3000`.

3. **Install backend dependencies**:
   - Navigate to the backend directory and install the required dependencies:
     ```bash
     npm install
     ```

4. **Run the backend API**:
   - Start the backend server:
     ```bash
     node server.js
     ```
   - The backend will be available at `http://localhost:5000`.

Make sure both the frontend and backend are running to fully interact with the application.

recording and ppt: https://northeastern-my.sharepoint.com/:f:/g/personal/jinkaradhakrishna_s_northeastern_edu/ErrmuoIisCZGnV3rD2F0pFkBJHQfJxWIeyGPCZfJJdZnfg?e=gZpSIx

## Team Members

- Aadarsh Ravi(ravi.add@northeastern.edu)
- Rohan Reddy Patlolla(patlolla.ro@northeastern.edu)
- Rahul Reddy Patlolla(patlolla.ra@northeastern.edu)
- Swathi Jinka Radhakrishna(jinkaradhakrishna.s@northeastern.edu)
