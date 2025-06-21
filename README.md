# 📦 Geocalc Fullstack – Containerisierte 3D-Geometrie-App

**Modul 347 – Dienst mit Containern anwenden**  
Autor: Peter Ngo | Kurs: 23-294-F / 23-295-F  
Abgabe: 21. Juni 2025

---

## 🧠 Projektidee

Eine containerisierte Fullstack-Applikation zur Eingabe, Berechnung und 3D-Visualisierung geometrischer Figuren. Die App besteht aus einem Angular-Frontend, einem Spring Boot Backend, einer PostgreSQL-Datenbank, Keycloak zur Authentifizierung sowie einem pgAdmin-Dashboard zur Datenbankverwaltung. Entwickelt und nutzbar im DevContainer.

---

## 🧩 Projektarchitektur

### 🔷 Frontend – Angular (geocalc-frontend)
- 3D-Visualisierung mit Three.js
- Authentifizierung via Keycloak
- REST-Anbindung ans Backend
- Komponenten: Login, ShapeInput, Calculation, Shape3DView, Results, AdminDashboard

### 🔶 Backend – Spring Boot (geocalc-backend)
- REST-API zur Berechnung von Volumen, Oberflächen etc.
- PostgreSQL-Datenbankanbindung über JPA/Hibernate
- Authentifizierung via Keycloak (OAuth2 / JWT)
- Swagger UI zur API-Dokumentation

### 🧱 Container-Services (Docker Compose)
| Service       | Beschreibung                                     |
|---------------|--------------------------------------------------|
| `postgres`    | Persistente PostgreSQL-Datenbank                 |
| `keycloak`    | Authentifizierungsserver mit Realm-Import        |
| `pgadmin`     | Web-GUI zur PostgreSQL-Administration            |
| `devcontainer`| Entwicklungscontainer für Angular & Spring       |

---

## 🚀 Starten der Applikation

### 🏗️ Lokaler Build & Start
Erstellt alle Images lokal:
```bash
docker compose -f docker/docker-compose-build.yml up --build
