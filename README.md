File Upload Application using Multer

A simple Node.js application that allows users to upload files through a web interface. The project uses Express.js, Multer, and EJS to handle file uploads and store files on the server with unique filenames.

```text

Features
Upload files from the browser
Store uploaded files on the server
Generate unique filenames using timestamps
Server-side rendering with EJS
Handle multipart/form-data requests
Simple and clean user interface
Tech Stack
Backend
Node.js
Express.js
Middleware
Multer
Frontend
EJS
HTML
CSS
Project Structure
file-upload-app/
│
├── uploads/
│   └── Uploaded Files
│
├── views/
│   └── homepage.ejs
│
├── index.js
├── package.json
├── package-lock.json
├── .gitignore
└── README.md
How It Works
User selects a file from the browser.
Form submits a POST request to /upload.
Multer processes the uploaded file.
File is stored inside the uploads folder.
A unique filename is generated using the current timestamp.
User is redirected back to the homepage.
Multer Configuration
Storage Engine
const storage = multer.diskStorage({
    destination: function(req,file,cb){
        return cb(null,'./uploads')
    },
    filename: function(req,file,cb){
        return cb(null,`${Date.now()}-${file.originalname}`)
    }
})
Upload Middleware
const upload = multer({ storage })
Single File Upload
app.post('/upload', upload.single('profileImage'), (req,res)=>{
    console.log(req.file)
    res.redirect('/')
})

```
