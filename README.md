# Cloud Disk

A full-stack cloud storage application built with MERN stack (MongoDB, Express, React, Node.js). Users can register, login, upload files, create folders, and manage their cloud storage.

## Features

- **User Authentication**: Secure registration and login with JWT
- **File Management**: Upload, download, and delete files
- **Folder Structure**: Create and navigate through folders
- **File Metadata**: Track file size, upload date, and other properties
- **Redux State Management**: Efficient client-side state handling
- **Responsive UI**: Clean interface with styled-components

## Tech Stack

### Backend
- **Node.js** - JavaScript runtime
- **Express** - Web framework
- **MongoDB** - NoSQL database with Mongoose ODM
- **JWT** - Authentication tokens
- **bcryptjs** - Password hashing
- **express-validator** - Input validation

### Frontend
- **React** - UI library
- **Redux** - State management with Redux Thunk
- **React Router** - Client-side routing
- **Axios** - HTTP client
- **styled-components** - CSS-in-JS styling
- **Moment.js** - Date/time formatting

## Project Structure

```
cloud-disk/
├── client/                 # React frontend
│   ├── public/
│   └── src/
│       ├── actions/        # Redux actions
│       ├── components/     # React components
│       ├── reducers/       # Redux reducers
│       ├── assets/         # Images and icons
│       ├── common/         # Shared utilities
│       └── App.js
│
└── server/                 # Node.js backend
    ├── config/             # Configuration files
    ├── controllers/        # Request handlers
    ├── middleware/         # Custom middleware
    ├── models/             # Mongoose schemas
    ├── routes/             # API routes
    ├── services/           # Business logic
    └── index.js
```

## Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- npm or yarn

### Backend Setup

1. Navigate to the server directory:
```bash
cd server
```

2. Install dependencies:
```bash
npm install
```

3. Configure environment:
   - Edit `config/default.json` with your settings:
   ```json
   {
     "serverPort": 5000,
     "dbUrl": "your-mongodb-connection-string",
     "secretKey": "your-secret-key",
     "filePath": "/path/to/store/files"
   }
   ```

4. Create the files directory:
```bash
mkdir -p /path/to/store/files
```

5. Start the server:
```bash
npm start
# or for development with auto-reload
npm run dev
```

### Frontend Setup

1. Navigate to the client directory:
```bash
cd client
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm start
```

The app will open at `http://localhost:3000`

## API Endpoints

### Authentication
- `POST /api/auth/registration` - Register a new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/auth` - Verify authentication token

### Files
- `GET /api/files` - Get user's files (supports parent folder query)
- `POST /api/files` - Create a new folder
- `POST /api/files/upload` - Upload a file
- `GET /api/files/download` - Download a file
- `DELETE /api/files` - Delete a file or folder

## Usage

1. **Register**: Create a new account with email and password
2. **Login**: Sign in with your credentials
3. **Upload Files**: Click upload button to add files to your storage
4. **Create Folders**: Organize files into folders
5. **Navigate**: Click on folders to navigate through your file structure
6. **Download**: Click download to save files locally
7. **Delete**: Remove files or folders you no longer need

## Security Features

- Password hashing with bcryptjs
- JWT-based authentication
- Protected API routes with auth middleware
- Input validation with express-validator
- CORS configuration

## Development

### Backend Development
```bash
cd server
npm run dev  # Runs with nodemon for auto-reload
```

### Frontend Development
```bash
cd client
npm start  # Runs with hot reload
```

### Building for Production
```bash
cd client
npm run build
```

## Environment Variables

Create appropriate configuration in `server/config/default.json`:

- `serverPort` - Port for backend server
- `dbUrl` - MongoDB connection string
- `secretKey` - JWT secret key
- `filePath` - Local path for file storage

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

ISC

## Author

Alberto M.

---

**Note**: Remember to never commit sensitive configuration files with real credentials to version control. Use environment variables or config files that are gitignored.
