# Tech Detector

Tech Detector is a Chrome extension and backend service that identifies the technology stack used by websites, similar to Wappalyzer.

## 📂 Project Structure

```
tech-detector/
├── backend/                # Golang backend for API & scraping
│   ├── cmd/               # Entry point (main.go)
│   ├── config/            # Configuration files (config.go, db.go)
│   ├── internal/          # Core application logic
│   │   ├── scraper/       # Web scraping logic (scraper.go, patterns.go)
│   │   ├── database/      # DB models and queries (models.go, repository.go)
│   │   ├── api/           # API routes & handlers (handlers.go, routes.go)
│   ├── pkg/               # Utility packages (logger, HTTP client)
│   ├── test/              # Unit tests for API & scraper
│   ├── .env               # Environment variables (ignored in Git)
│   ├── go.mod, go.sum     # Go dependencies
│   ├── Dockerfile         # Docker setup for backend
│   ├── README.md          # Backend-specific documentation
│
├── chrome-extension/      # Chrome extension code
│   ├── src/               # JavaScript source files
│   │   ├── background.js  # Background script
│   │   ├── content.js     # Content script
│   │   ├── popup.js       # Popup script
│   │   ├── manifest.json  # Extension metadata
│   ├── assets/            # Icons & images
│   ├── README.md          # Extension-specific documentation
│
├── database/              # SQL schema & migrations
│   ├── schema.sql         # Database schema definition
│   ├── seed.sql           # Initial data seeding
│   ├── README.md          # Database documentation
│
├── deployment/            # Deployment configs
│   ├── railway/           # Railway deployment config
│   ├── render/            # Render deployment config
│   ├── flyio/             # Fly.io deployment config
│   ├── README.md          # Deployment instructions
│
├── docker-compose.yml     # Docker configuration for local development
├── .gitignore             # Files to ignore in Git
├── README.md              # Main project documentation
```

## ✅ Progress So Far

### 1️⃣ Backend Setup
- **Initialized the project structure** (`backend/`, `cmd/`, `config/`, `internal/`).
- **Set up Go modules** using `go mod init`.
- **Installed dependencies**:
  ```sh
  go get github.com/gin-gonic/gin      
  go get github.com/joho/godotenv       
  go get github.com/lib/pq              
  go get github.com/gocolly/colly      
  go get github.com/sirupsen/logrus      
  go mod tidy
  ```
- **Created a basic API** (`cmd/main.go`) with a `/health` endpoint:
  ```go
  r.GET("/health", func(c *gin.Context) {
      c.JSON(200, gin.H{"status": "API is running"})
  })
  ```
- **Verified API is running** on `http://localhost:8080/health`.
- **Pushed project to GitHub** at [Divalsehgal/tech-detector](https://github.com/Divalsehgal/tech-detector).

## 🚀 Next Steps
- [ ] **Step 2: Setup PostgreSQL Database**
- [ ] **Step 3: Implement Scraper for Tech Detection**
- [ ] **Step 4: Build the Chrome Extension UI**