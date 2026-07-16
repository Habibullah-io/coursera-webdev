# FOOD LLC
A modern, nature-inspired restaurant website built with Vanilla HTML/CSS, Bootstrap, and scroll animations.
## Features
- **Design System:** Custom CSS variables for easy theming
- **Theme:** Nature-inspired, organic shapes via `clip-path`, earthy and vibrant custom colors
- **Typography:** Playfair Display & Lora
- **Animations:** Intersection Observer for scroll-reveals, staggered lists, and hover lifts
- **Dark Mode:** Built-in toggle using Bootstrap 5 data-bs-theme
- **Responsive:** Mobile-first layout with responsive dot-navigation
## Setup Instructions for VPS
This project is entirely static (HTML, CSS, JS). You can serve it using any web server like Nginx, Apache, or a Node.js static server.
### Using Nginx (Recommended)
1. Clone or copy the project files to your VPS (e.g., `/var/www/food-llc`).
2. Configure your Nginx server block:
```nginx
server {
    listen 80;
    server_name foodllc.com www.foodllc.com;
    root /var/www/food-llc;
    index index.html;
    location / {
        try_files $uri $uri/ =404;
    }
    # Cache static assets
    location ~* \.(jpg|jpeg|png|gif|ico|css|js)$ {
        expires 30d;
        add_header Cache-Control "public, no-transform";
    }
}
```
3. Reload Nginx: `sudo systemctl reload nginx`
### Structure
```
/
├── index.html        # Main single-page application
├── style.css         # Custom styles and design variables
├── README.md         # This documentation
├── .env.example      # Example environment variables (for backend integrations if added)
└── public/
    └── images/       # Static image assets (hero, food images)
```
## Future Backend Integrations
Currently, the Contact and Booking actions use `mailto:` links. If you add a backend (like Node/Express or PHP), you can map the `.env` file variables to configure your SMTP or database.
