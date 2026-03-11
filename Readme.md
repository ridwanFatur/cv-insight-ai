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
- **Backend**: Powered by FastAPI, connected to PostgreSQL for data storage and RabbitMQ for task queuing. Handles WebSocket communication with the frontend and uploads files to Google Cloud Storage (GCS).  
🔗 [Backend Repository](https://github.com/ridwanFatur/cv-insight-ai-backend).
- **Worker**: A Python service that consumes tasks from RabbitMQ, invokes Google Generative AI, and processes PDF files stored in GCS.  
🔗 [Worker Repository](https://github.com/ridwanFatur/cv-insight-ai-worker).

### CI/CD
Each service is equipped with its own CI/CD pipeline, enabling automated deployment and testing.
> ⚠️ Note: While the project is fully deployable, free-tier cloud resources are insufficient for live hosting. Therefore, the README showcases screenshots and recorded videos to demonstrate the functionality.
