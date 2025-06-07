# simple-gallerie

A simple gallerie for photographers

## Project Scope and Features

Before coding, clarify the core features to keep your project focused and achievable. For a photo gallery platform, consider:
User Roles:
Photographers: Can register, upload photos, set prices, and manage their portfolio.

Clients: Can browse photos, purchase digital downloads or prints, and view photographer profiles.

### Core Features:

- User authentication (sign-up, login, logout).
- Photo upload and management (upload, delete, edit metadata like title, price, tags).
- Gallery display (public gallery for browsing photos).
- Shopping cart and checkout (basic payment integration).
- Search and filter (by tags, photographer, or category).

#### Learning Goals:

- Angular: Components, services, routing, forms, and HTTP requests.
- Web Dev: REST API integration, file uploads, basic security, and responsive design.
- Optional: Basic backend development (e.g., Node.js or Firebase).

For a learning project, start with a minimal viable product (MVP):

1. Photographer can upload and display photos.
2. Clients can browse photos and “buy” them (mock checkout without real payments initially).
3. Basic user authentication.

## Setting up the Evironment

To work with Angular and web development, you’ll need the right tools. Here’s how to set up:
Install Node.js and npm: Angular requires Node.js (LTS version recommended, e.g., 20.x). Download it from nodejs.org. npm comes with Node.js and is used to manage packages.

**Install Angular CLI:** Run the following command to install the Angular Command Line Interface globally:

```bash
npm install -g @angular/cli
```

### Code Editor: Use Visual Studio Code (VS Code) with extensions like:

Angular Language Service (for Angular template support).

- Prettier (for code formatting).
- ESLint (for ensures code quality).

### Version Control: Set up Git and create a repository on GitHub to track your code. Initialize your project with:

```bash
git init
git add .
git commit -m "Initial commit"
```

### Docker

Run all components.

### Quarkus

To run our backend logic.

### Keycloak

User managements and Tokens.

### PostgreSQL

**Browser:** Use Chrome or Firefox with developer tools for debugging and testing.

## Project Architecture

### Frontend (Angular):

Handles UI, photo uploads, and gallery display.

Communicates with the Quarkus backend via REST APIs.

Uses Keycloak’s JavaScript adapter to manage authentication (login, token handling).

### Backend (Quarkus):

Exposes REST endpoints for photo management (upload, list, delete).

Integrates with Keycloak to secure endpoints and verify JWT tokens.

Stores photo metadata in a database (e.g., PostgreSQL) and images in a file system or cloud storage (e.g., AWS S3 or MinIO).

### Keycloak:

Manages user authentication and issues JWT tokens.

Defines roles (e.g., photographer, client) for authorization.
Runs as a separate service, typically in a Docker container.

# Angular

- is a opinionated framework not a library
- has built-in cli
- has tools and libraries installed out of the box to serve medium size applications

## Environment

```bash
# install the @angular/cli
npm install -g @angluar/cli

# check cli version
ng --version

# create an app
ng new first-ng-app # optionally use --dry-run

# create an app with some configuration
ng new first-ng-app --inline-styles --inline-template

# help / show all available opptions
ng new --help
```

## Creating an Angular Application

## project file structure

`index.html`
The top level component `app-root`

`main.ts`
generates or creates the angular application using the app-component.

`syles.scss`
the application style sheets

## Core Concepts

- Components
- Directive. Pipes
- Data-Binding, Event Handlers
- Http Module, Forms Module
- Routing and Animations
- Testing and Building for productions

### Components

Angular components are the building blocks that comprise the angula component.

```bash
ng g c header # short form
ng generate component header # full form to generate the component 'header'

# OR (in a nested directory)
ng g c components.header
#created fheader Comnonent inside the src/app/components folder
```

```typescript
import { Component } from "@angular/core";

// component decorator
@Component({
  selector: "app-root", // the tag that stands for this component
  templateUrl: "./app.component.html",
  styleUrls: ["./app.component.css"],
})
export class AppComponent {
  title = "photo-callerie";
}
```

## Update from one version to another

There is in update guide where you can choose from which version to which version and you get step by step instructions.

# Quarkus

Besided Quarkus being a trendy technology that is worth learning it comes with some benefits which are valuable for the project that
could speed up development by combingin all relevant components in one quarkus instance and all of the support live reloading of changes, this could be quite a development boost.

- **Live Reloading of changes** - in dev mode quarkus will detect changed files and i again hit with a request this changes will be detected and the code rebuild/reloaded
- **Angular Support** - via the quinoa plugin, angular frontends get get directly deployed with quarkus, so we can skip using node for a while
- **End to End Tests** - end to end test in a single container ?

## Installing

[Quarkus - Getting Started](https://quarkus.io/guides/getting-starte://quarkus.io/guides/getting-started)

```
mvn io.quarkus.platform:quarkus-maven-plugin:3.23.0:create \
    -DprojectGroupId=org.acme \
    -DprojectArtifactId=getting-started \
    -Dextensions='rest'
cd getting-started
```

**starting in dev mode**

```
./mvnw quarkus:dev
```

### Database

**installing psql on the mac**

```
brew doctor
brew update
brew install libpq
```

```
brew link --force libpq
```

```
truehl@Thorstens-MacBook-Pro-2 ~ % psql --version
psql (PostgreSQL) 17.5

```

```
postgresql://quarkus:quarkus@localhost:62474
```

#### Hiberante

[Quarkus-Hibernate Turial](https://www.youtube.com/watch?v=tsBW6Bed46M)
[hibernat-orm docs](https://quarkus.io/guides/hibernate-orm)

### Youtube

[Quarkus - Bootstrap Project](http://code.quarkus.io)
[nodejs vs quarkus quinoa](https://www.youtube.com/live/00g-gBIYpsU?si=95FjD4F-WOFXFGde)
[Quarkus and Playwright](https://docs.quarkiverse.io/quarkus-playwright/dev/index.html)
