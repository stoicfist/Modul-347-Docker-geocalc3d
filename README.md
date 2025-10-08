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

### 📁 Hinweis: Git-Submodule

    Das Projekt verwendet Git-Submodule für geocalc-frontend und geocalc-backend.
    Um den vollständigen Quellcode nach dem Klonen sichtbar zu machen, führe bitte zusätzlich folgenden Befehl im Terminal aus:
    git submodule update --init --recursive

    Alternativ:
    Wenn du das ZIP heruntergeladen hast, kann es sein, dass die Submodule fehlen. In diesem Fall musst du das Projekt über Git klonen:
    git clone --recurse-submodules https://github.com/stoicfist/Modul-347-Docker-geocalc3d.git


    

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

docker compose -f docker/docker-compose-build.yml up --build


## ☁️ Start mit Docker-Hub-Images

Alternativ zum lokalen Build können die Container auch direkt aus der Docker Registry geladen und gestartet werden:

```bash
docker compose -f docker/docker-compose-hub.yml up

---

## 🔗 Nützliche Links während der Entwicklung

| Dienst       | URL                                               | Beschreibung                            |
|--------------|---------------------------------------------------|-----------------------------------------|
| Frontend     | [http://localhost:4200](http://localhost:4200)    | Angular App Startseite                  |
| Backend API  | [http://localhost:8080](http://localhost:8080)    | Spring Boot Backend                     |
| Swagger UI   | [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html) | API Dokumentation / Testing             |
| Keycloak     | [http://localhost:8080](http://localhost:8080)    | Admin Console Login (Realm: `geocalc`)  |
| pgAdmin      | [http://localhost:5050](http://localhost:5050)    | PostgreSQL Verwaltung                   |
