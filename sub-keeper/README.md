📦 Sub Keeper
Sub Keeper is a modern subscription management dashboard built with React, TypeScript, Tailwind CSS, and powered by Vite. It helps users organize, view, and track their active and upcoming subscriptions in a streamlined UI.

🚀 Features
💡 Add and manage multiple subscriptions

📅 Track upcoming renewals and payment dates

🎨 Responsive UI with Tailwind CSS

⚡ Fast development and build using Vite

🛠️ Built with Bun (optional Node.js compatible)

   Authentication mention

   User data storage notes

   Recommendations for secure storage (since handling passwords must be secure)



🧰 Tech Stack
Tool/Tech	Purpose
React + TypeScript	Frontend logic & UI
Tailwind CSS	Styling
Vite	Fast development/build
Bun (optional)	Package management/runtime

📁 Project Structure
csharp
Copy
Edit
sub-keeper-main/
│
├── public/              # Static assets
├── src/                 # Main application files
│   ├── App.tsx          # Main app component
│   ├── main.tsx         # App entry point
│   └── styles/
│
├── index.html           # Root HTML template
├── tailwind.config.ts   # Tailwind configuration
├── tsconfig.json        # TypeScript configuration
├── vite.config.ts       # Vite setup
└── package.json         # Project dependencies & scripts

🔐 User Authentication

The application includes a basic login system to store **user ID and password**. This version uses:

- 🔒 **Insecure LocalStorage** (for learning/demo purposes only)
- 🧪 You can enter a user ID and password, and it will be stored in the browser
- 🚫 **Do NOT use LocalStorage for production credentials**
- ✅ Recommended: Integrate Firebase Auth, Supabase, or custom backend with hashing

### Authentication Flow

1. User visits login page
2. Enters `user ID` and `password`
3. Data is stored in browser's `localStorage`
4. On next visit, user is auto-logged in (until manually logged out or storage is cleared)

⚠️ Security Note
This project currently stores user credentials in localStorage, which is not secure for production.

🔐 For secure authentication:

Use bcrypt to hash passwords

Store data in a backend (Node.js, Firebase, Supabase, etc.)

Use HTTPS & secure cookies / JWT tokens

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Security Features

- Password hashing with bcrypt
- JWT token authentication
- Input validation and sanitization
- CORS configuration
- Security headers with Helmet
- Protected API routes

### Subscription Model.
```javascript
{
  user: ObjectId (ref: User),
  name: String,
  description: String,
  amount: Number,
  currency: String,
  billingCycle: String,
  nextBillingDate: Date,
  category: String,
  status: String,
  website: String,
  notes: String,
  autoRenew: Boolean,
  paymentMethod: String,
  timestamps: true
}

## Database Schema

### User Model
```javascript
{
  name: String,
  email: String (unique),
  password: String (hashed),
  avatar: String,
  isActive: Boolean,
  timestamps: true
}



