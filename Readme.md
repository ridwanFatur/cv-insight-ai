## CV INSIGHT AI

CV INSIGHT AI is a mini microservices project designed to provide AI-powered feedback on uploaded CVs.  
The system is structured with frontend, backend, and worker services, each with its own responsibilities and CI/CD pipelines.

### Features
- **Google Login**: Users can log in using their Google account.
- **CV Upload**: Users can upload CVs in PDF format.
- **AI-Generated Feedback**: Once uploaded, the CV is processed by AI and feedback is returned to the user.

### Architecture
- **Frontend**: Built with React, TailwindCSS, and TypeScript. Uses TanStack Query for caching and WebSocket for real-time updates.  
🔗 [Frontend Repository](https://github.com/ridwanFatur/cv-insight-ai-frontend).
- **Backend**: Powered by FastAPI. Uses PostgreSQL as the primary database and Alembic for database migrations. Handles WebSocket communication with the frontend and uploads files to Google Cloud Storage (GCS). Tasks are queued in RabbitMQ.  
🔗 [Backend Repository](https://github.com/ridwanFatur/cv-insight-ai-backend).
- **Worker**: A Python service that consumes tasks from RabbitMQ, invokes Google Generative AI, and processes PDF files stored in GCS.  
🔗 [Worker Repository](https://github.com/ridwanFatur/cv-insight-ai-worker).

### Containerization
All services are container-based, with each service having its own Dockerfile. A ready-to-run docker-compose setup allows you to spin up the full stack locally for testing or development.

### CI/CD
Each service is equipped with its own CI/CD pipeline, enabling automated deployment. The pipelines are configured to use:  
- Google Secret Manager and GitHub Secrets for managing sensitive configurations.
- SSH access to Google Compute Engine (GCE) VMs for deployment.
- Service accounts to push and pull images from Google Artifact Repository.
- Secure environment variables for credentials, API keys, and other sensitive config needed during build and deployment.

> ⚠️ Note: While the project is fully deployable, free-tier cloud resources are insufficient for live hosting. Therefore, the README showcases screenshots to demonstrate the functionality.
