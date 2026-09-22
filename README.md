# Amazon-Style Registration Form

A polished, responsive **Amazon-style account registration UI** built as a standalone HTML project. It demonstrates client-side form validation, password-strength feedback, loading states, success feedback, responsive design, and optional submission to a Google Apps Script Web App endpoint.

> **Educational / demo project:** This project is not an official Amazon application and is not affiliated with, endorsed by, or sponsored by Amazon. Do not use real passwords, personal credentials, or sensitive information with the demo endpoint.

## ✨ Features

- Responsive registration form for desktop and mobile screens
- Amazon-inspired visual design and color palette
- Name, email, password, country, state/province, and city fields
- Client-side validation with inline error messages
- Password show/hide control
- Live password-strength indicator
- Loading spinner while the form is submitted
- Toast notifications for success and network errors
- Animated account-created success panel
- Automatically generated-looking user ID display (`USR-****`)
- Keyboard-friendly form navigation
- Accessible labels, status messages, and focus states
- Optional Google Apps Script Web App integration
- No build system or framework required

## 📁 Project Structure

```text
krishana_project/
├── index.html       # Complete application: HTML, CSS, and JavaScript
├── output_qr.png    # QR image included with the project
└── README.md        # Project documentation
```

## 🚀 Getting Started

### 1. Download or extract the project

Extract the project folder to your computer.

### 2. Open the application

The project is a static web page, so you can open `index.html` directly in a modern browser.

For a better development experience, you can also serve the folder with a local web server.

Example with Python:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## 🧪 How to Use

1. Enter a name.
2. Enter a valid email address.
3. Enter a password of at least 8 characters.
4. Select a country.
5. Enter a state/province and city.
6. Review the validation messages if any field is incomplete.
7. Submit the form.

The page displays a success panel after the submission request is initiated.

## 🔐 Security & Privacy Notice

This is an educational front-end demonstration. The current implementation sends the following form data to the configured Google Apps Script Web App endpoint:

- Name
- Email
- Password
- Country
- State/province
- City

**Do not enter real passwords or sensitive personal information.** A production authentication system should never send or store plaintext passwords through a simple client-side webhook.

For a real application, use a secure backend with:

- HTTPS/TLS
- Server-side validation
- Password hashing with a modern password-hashing algorithm such as Argon2id or bcrypt
- Secure session management
- CSRF protection where applicable
- Rate limiting and abuse protection
- Proper authentication and account-recovery flows
- Secure secret/key management
- Appropriate privacy and data-retention controls

## 🔗 Google Apps Script Integration

The form currently uses the `WEBHOOK_URL` constant inside `index.html`:

```javascript
const WEBHOOK_URL = "YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL";
```

To connect your own backend/demo endpoint, replace the value with your deployed Google Apps Script Web App URL.

The submission uses:

```javascript
fetch(WEBHOOK_URL, {
  method: "POST",
  mode: "no-cors",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify(data),
});
```

Because `no-cors` is used, the browser cannot read the response body. The current UI therefore treats a completed `fetch()` call as a successful submission attempt rather than verifying a server-side response.

## 🛠️ Customization

Most of the project is contained in `index.html`, including the CSS and JavaScript.

### Change the title

Edit the `<title>` element:

```html
<title>Your Project Name</title>
```

### Change the colors

The main colors are defined in the CSS `:root` section near the top of `index.html`.

### Change form fields

Add or remove fields in the form and update the `data` object and `validate()` function in the JavaScript section.

### Change the webhook

Update `WEBHOOK_URL` with your own endpoint. Never commit private API keys, service-account credentials, or other secrets to a public repository.

## 🌐 Browser Compatibility

The project is designed for modern browsers that support:

- HTML5
- CSS3
- JavaScript ES2017+
- `fetch()`
- CSS Grid and Flexbox

Recommended browsers include current versions of Chrome, Edge, Firefox, and Safari.

## 📱 Responsive Design

The layout adapts to smaller screens. On narrow screens, the state/city two-column section changes to a single-column layout and the card spacing is reduced for easier mobile use.

## 🧩 Technologies Used

- **HTML5** — page structure and form controls
- **CSS3** — layout, responsive styling, animations, and visual effects
- **Vanilla JavaScript** — validation, UI state, password strength, and submission
- **Google Apps Script Web App** — optional demo backend/webhook
- **Google Fonts / Inter** — typography

No frontend framework or package manager is required.

## ⚠️ Brand Notice

This project intentionally uses an Amazon-inspired interface for educational purposes. **Amazon**, its logo, product names, and related trademarks belong to their respective owners. This project is not an official Amazon website or service.

For a public deployment, consider replacing Amazon branding, copy, links, and trademarks with original project branding.

## 📄 License

No separate license is currently included. If you plan to publish or redistribute the project, add an appropriate license and ensure that all third-party assets, branding, fonts, and code are used according to their respective terms.

## 👨‍💻 Author

**Krishna**

Built as a web-development / form-handling demonstration project.
