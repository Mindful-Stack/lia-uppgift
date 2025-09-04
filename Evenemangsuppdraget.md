## 🧪 Utvecklingsuppgift: Local Events Directory

### 🎯 Syfte
Ni ska bygga en enkel CRUD-applikation där användare kan hantera lokala evenemang. Applikationen består av:

- Ett backend-API i **.NET 9** med **Minimal API** och **Vertical Slice Architecture** (i Visual Studio, skapa ett .NET Core WebAPI projekt)
  => Titta gärna i "*grantigo*" repositoryt hur detta implementeras via IEndpoint interface och IEndpointRouteBuilderExtensions. (Sökväg: src/server/Grantidote.Api/Endpoints/_internal/)
- En frontend byggd med **SvelteKit**
- En databas i **PostgreSQL**, hanterad via **Entity Framework Core**
- Frontend kommunicerar med backend via API-anrop

Ingen autentisering behövs.

---

## 🧱 Backend (.NET 9 Minimal API)

### 📁 Enkel mappstruktur (Vertical Slice)

```plaintext
src/
│
├── Events/
│   ├── CreateEvent.cs
│   ├── GetEvents.cs
│   ├── UpdateEvent.cs
│   ├── DeleteEvent.cs
│   └── Event.cs
│
├── Categories/
│   ├── CreateCategory.cs
│   ├── GetCategories.cs
│   ├── UpdateCategory.cs
│   ├── DeleteCategory.cs
│   └── Category.cs
│
├── Data/
│   └── AppDbContext.cs
│
│
└── Program.cs
```

### 🧩 Funktioner

- CRUD för **Event**: skapa, hämta, uppdatera, ta bort
- CRUD för **Category**
- Filtrera events efter kategori eller datum (valfritt)

---

### 🧪 API-testning med Scalar

För att dokumentera och testa era endpoints, ska ni använda **Scalar**.

nuget paketet Scalar.ASPNetCore behöver installeras via nuget package manager

Titta gärna i "*grantigo*" repositoryt hur Scalar implementeras i Program.cs (API-projektet).

---

## 🎨 Frontend (SvelteKit)

### 📄 Sidor

- `+page.svelte` – Lista alla events
- `add-event/+page.svelte` – Formulär för att lägga till event
- `categories/+page.svelte` – Hantera kategorier
- `filter/+page.svelte` – Filtrera events

### 📡 API-anrop

Använd `fetch` eller `load` för att hämta data från backend. Exempel:

```js
const res = await fetch('http://localhost:5000/events');
const events = await res.json();
```

---

## 🧠 Tips till er

- Det är att föredra att har både client och server projekt i samma mapp, precis som Grantigo.
- Börja med att skapa databasen och entiteterna i backend
- Implementera endpoints en i taget, testa med Scalar
- Bygg frontend-sidor som anropar API:et och visar data (använd er av Svelte turorialen för mappstrukturen)
- Håll koden modulär – varje slice (feature) ska ha sin egen fil

---
