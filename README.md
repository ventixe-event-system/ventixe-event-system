 Ventixe Event System - MVP

Ett komplett microservices-baserat event-hanteringssystem byggt med React frontend och ASP.NET Core backend APIs.

📋 Projektöversikt
Ventixe är en modern event-plattform som gör det möjligt för användare att:
- Hantera och visa events
- Boka biljetter till events
- Lämna feedback och betyg
- Se statistik och dashboard

🏗️ Systemarkitektur:
 Microservices Design
┌─────────────────┐    ┌──────────────────┐    ┌──────────────────┐
│   Frontend      │    │   User Service   │    │  	Event Service  │
│   (React)       │◄──►│   (ASP.NET)      │    │   	(ASP.NET)     │
│   Port 3000     │    │   Port 5271      │    │   	Port 5272     │
└─────────────────┘    └──────────────────┘    └──────────────────┘


📁 Repository Struktur
- [ventixe-frontend](https://github.com/ventixe-event-system/ventixe-frontend) - React frontend applikation
- [ventixe-user-service](https://github.com/ventixe-event-system/ventixe-user-service) - Användarhantering och autentisering
- [ventixe-event-service](https://github.com/ventixe-event-system/ventixe-event-service) - Event- och bokningshantering

⚙️ Teknologier
Frontend
- React 18 - Användarinterface
- CSS3 - Styling och animations
- Fetch API - HTTP kommunikation
- LocalStorage - Klientside datalagring

 Backend
- ASP.NET Core 8 - Web API framework
- Entity Framework Core - ORM för databasaccess
- SQLite - Lightweight databas
- BCrypt* - Lösenordshashing
- CORS - Cross-origin resource sharing

🚀 Installation och körning
Förutsättningar
- Node.js (v18+)
- .NET 8 SDK
- Visual Studio eller VS Code

Starta systemet lokalt

1. Klona repositories:

bash
git clone https://github.com/ventixe-event-system/ventixe-frontend.git
git clone https://github.com/ventixe-event-system/ventixe-user-service.git
git clone https://github.com/ventixe-event-system/ventixe-event-service.git


2. Starta User Service:

bash
cd ventixe-user-service
dotnet run
(Körs på: http://localhost:5271)


3. Starta Event Service:

bash
cd ventixe-event-service
dotnet run
(Körs på: http://localhost:5272)


4. Starta Frontend:

bash
cd ventixe-frontend
npm install
npm start
(Körs på: http://localhost:3000)


👤 Demo-användare
- Email: orlando@ventixe.se
- Lösenord: password123
- Roll: Admin

🎭 Funktionalitet
✅ Dashboard
- Översikt av systemstatistik
- Kommande events (345)
- Total bokningar (1,798)
- Sålda biljetter (1,250)
- Försäljningsintäkter ($348,805)
- Populära eventkategorier

✅ Events
- Lista alla tillgängliga events
- Filtrera per kategori (Music, Sports, Fashion, etc.)
- Sökfunktion
- Detaljerad eventinformation
- Realtid bokningssystem
- Biljetträknare

✅ Feedback
- Lämna betyg (1-5 stjärnor)
- Skriv kommentarer om events
- Se andras feedback
- Genomsnittsbetyg för events

🔗 API Endpoints
 User Service (Port 5271)
- POST /api/Auth/login - Användarinloggning
- POST /api/Auth/register - Registrera ny användare
- GET /api/Auth/test - Test endpoint

 Event Service (Port 5272)
- GET /api/Events - Hämta alla events
- GET /api/Events/{id} - Hämta specifikt event
- POST /api/Events/book - Boka biljetter
- GET /api/Events/categories - Hämta kategorier
- GET /api/Events/stats - Systemstatistik

  Databasschema
Users (User Service)

sql
- Id (Primary Key)
- Name
- Email (Unique)
- PasswordHash
- Role
- CreatedAt
- UpdatedAt


Events (Event Service)

sql
- Id (Primary Key)
- Title
- Description
- Category
- Date
- Time
- Location
- Price
- Status
- Color
- MaxTickets
- SoldTickets
- CreatedAt
- UpdatedAt


Bookings (Event Service)

sql
- Id (Primary Key)
- EventId (Foreign Key)
- UserId
- Tickets
- TotalPrice
- BookingDate
- Status

👨‍💻 Utvecklare

Skapat som MVP (Minimum Viable Product) för en microservices-arkitektur kurs.

*GitHub Organization:* [ventixe-event-system](https://github.com/ventixe-event-system)

📄 Licens
Detta projekt är skapat för utbildningssyfte.

---
*Byggt med ❤️ och mycket kaffe ☕*
