FROM mcr.microsoft.com/devcontainers/java:21

# Node.js für Angular
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash - \
  && apt-get update \
  && apt-get install -y nodejs

# Angular CLI installieren
RUN npm install -g @angular/cli

# Optional: Maven (falls nicht vorhanden im Base-Image)
RUN apt-get install -y maven

WORKDIR /workspace
