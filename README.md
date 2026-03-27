# Customisable-website
A customisable website for mobile application 
@import './variables';
@import './mixins';

.customizer-wrapper {
  @include flex-center;
  min-height: 100vh;
  background-color: $gray-100;

  @include md {
    display: flex;
  }
}

// Preview Section
.preview-pane {
  flex: 1;
  overflow-y: auto;
  max-height: 100vh;
  @include custom-scrollbar($gray-100, $gray-400);

  @include md {
    flex: 1;
  }
}

// Header Section
.preview-header {
  padding: $spacing-3xl $spacing-lg;
  text-align: center;
  position: relative;
  overflow: hidden;
  color: white;

  @include md {
    padding: $spacing-3xl;
  }

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    opacity: 0.1;
    z-index: 0;
  }

  .header-content {
    position: relative;
    z-index: 10;
  }

  h1 {
    margin-bottom: $spacing-md;
    font-weight: $font-weight-bold;
    transition: font-size $transition-base;
  }

  p {
    font-size: $font-size-xl;
    opacity: 0.9;
    margin-bottom: 0;
  }
}

// Section
.preview-section {
  padding: $spacing-2xl $spacing-lg;
  text-align: center;

  @include md {
    padding: $spacing-2xl;
  }

  &.hero {
    h2 {
      margin-bottom: $spacing-lg;
      font-weight: $font-weight-bold;
    }

    p {
      font-size: $font-size-lg;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
      opacity: 0.85;
    }
  }
}

// Features Grid
.features-grid {
  @include grid-responsive();
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;

  .feature-card {
    padding: $spacing-lg;
    border-radius: $radius-lg;
    border-left: 4px solid;
    transition: all $transition-base;

    &:hover {
      transform: translateY(-4px);
      box-shadow: $shadow-lg;
    }

    h3 {
      margin-bottom: $spacing-md;
      font-size: $font-size-lg;
      font-weight: $font-weight-bold;
    }

    p {
      font-size: $font-size-sm;
      opacity: 0.75;
      margin-bottom: 0;
    }
  }
}

// CTA Section
.cta-section {
  padding: $spacing-2xl $spacing-lg;
  text-align: center;

  @include md {
    padding: $spacing-2xl;
  }

  .btn {
    padding: 1rem 2rem;
    font-size: $font-size-lg;
    font-weight: $font-weight-bold;

    &:hover {
      box-shadow: $shadow-xl;
    }
  }
}

// Footer
.preview-footer {
  padding: $spacing-2xl $spacing-lg;
  text-align: center;
  margin-top: $spacing-2xl;

  @include md {
    padding: $spacing-2xl;
  }

  p {
    margin-bottom: 0;
  }
}

// Control Panel
.control-panel {
  width: 100%;
  max-height: 100vh;
  overflow-y: auto;
  background-color: $white;
  border-left: 1px solid $gray-200;
  padding: $spacing-lg;
  box-shadow: $shadow-xl;

  @include custom-scrollbar($white, $gray-300);

  @include md {
    width: 320px;
  }

  h2 {
    font-size: $font-size-2xl;
    font-weight: $font-weight-bold;
    margin-bottom: $spacing-lg;
    color: $gray-900;
  }
}

// Control Section
.control-section {
  margin-bottom: $spacing-lg;

  &:not(:last-child) {
    padding-bottom: $spacing-lg;
    border-bottom: 1px solid $gray-200;
  }

  h3 {
    font-size: $font-size-sm;
    font-weight: $font-weight-bold;
    color: $gray-700;
    margin-bottom: $spacing-md;
    text-transform: uppercase;
    letter-spacing: 0.05em;
  }
}

// Color Control
.color-control {
  margin-bottom: $spacing-md;

  label {
    display: block;
    font-size: $font-size-sm;
    font-weight: $font-weight-medium;
    color: $gray-600;
    margin-bottom: $spacing-xs;
  }

  .color-input-group {
    display: flex;
    gap: $spacing-md;
    align-items: center;

    input[type='color'] {
      width: 48px;
      height: 48px;
      padding: 2px;
      border: 2px solid $gray-200;
      border-radius: $radius-base;
      cursor: pointer;

      &:hover {
        border-color: $primary-color;
      }
    }

    input[type='text'] {
      flex: 1;
      padding: $spacing-xs $spacing-sm;
      border: 1px solid $gray-200;
      border-radius: $radius-base;
      font-size: $font-size-sm;
      font-family: $font-mono;

      @include focus-ring;
    }
  }
}

// Select Input
.select-control {
  select {
    width: 100%;
    padding: $spacing-xs $spacing-sm;
    border: 1px solid $gray-200;
    border-radius: $radius-base;
    background-color: $white;
    color: $gray-700;
    font-size: $font-size-sm;

    @include focus-ring;
  }
}

// Button Group
.button-group {
  display: flex;
  gap: $spacing-md;

  .btn-toggle {
    flex: 1;
    padding: $spacing-xs $spacing-sm;
    border: none;
    border-radius: $radius-base;
    font-size: $font-size-sm;
    font-weight: $font-weight-medium;
    cursor: pointer;
    transition: all $transition-base;
    background-color: $gray-100;
    color: $gray-700;

    &:hover {
      background-color: $gray-200;
      transform: none;
      box-shadow: none;
    }

    &.active {
      background-color: #3b82f6;
      color: $white;
    }

    @include focus-ring;
  }
}

// Export Button
.export-button {
  width: 100%;
  padding: $spacing-md $spacing-lg;
  background-color: $gray-900;
  color: $white;
  border: none;
  border-radius: $radius-lg;
  font-size: $font-size-base;
  font-weight: $font-weight-semibold;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: $spacing-md;
  transition: all $transition-base;

  &:hover {
    background-color: $gray-800;
    transform: translateY(-2px);
    box-shadow: $shadow-lg;
  }

  &:active {
    transform: translateY(0);
  }

  @include focus-ring;

  svg {
    width: 18px;
    height: 18px;
  }
}

// Responsive - Stack on mobile
@include md {
  .customizer-wrapper {
    flex-direction: row;
  }

  .control-panel {
    width: 320px;
    border-left: 1px solid $gray-200;
    padding: $spacing-lg;
  }
}

@media (max-width: 768px) {
  .customizer-wrapper {
    flex-direction: column;
  }

  .preview-pane {
    max-height: 60vh;
  }

  .control-panel {
    width: 100%;
    max-height: 40vh;
    border-left: none;
    border-top: 1px solid $gray-200;
    padding: $spacing-md;
  }

  .preview-header {
    padding: $spacing-2xl $spacing-md;
  }

  .preview-section {
    padding: $spacing-xl $spacing-md;
  }

  h1 {
    @include responsive-font($font-size-2xl, $font-size-3xl, $font-size-4xl);
  }

  h2 {
    @include responsive-font($font-size-xl, $font-size-2xl, $font-size-3xl);
  }
}
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Tiara Beauty Brand</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Welcome to Tiara Beauty!</h1>
    </header>
    <main>
        <p>Here you can find the best beauty products tailored just for you.</p>
    </main>
    <footer>
        <p>&copy; 2026 Tiara Beauty Brand. All rights reserved.</p>
    </footer>
</body>
</html>#!/bin/bash

# Deploy script for Tiara Beauty Brand

# Build the application
echo "Building the application..."
# Add your build commands here

# Deploy the application
echo "Deploying the application..."
# Add your deployment commands here
from flask import Flask, request

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def webhook():
    data = request.json
    # Handle the received data
    print(data)
    return '', 200

if __name__ == '__main__':
    app.run(port=5000)[Unit]
Description=Tiara Webhook Service
After=network.target

[Service]
ExecStart=/usr/bin/python3 /path/to/webhook-receiver.py
Restart=always

[Install]
WantedBy=multi-user.targetserver {
    listen 80;
    server_name your_domain.com;

    location / {
        proxy_pass http://localhost:5000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}# DEPLOYMENT.md

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/tiarasaran25/tiara-website.git
   cd tiara-websitepython3 -m venv venv
source venv/bin/activatepip install -r requirements.txtsudo systemctl start tiara-webhook.servicesudo journalctl -u tiara-webhook.serviceTiara Beauty Brand - Official Website# Clone your new repository
git clone https://github.com/tiarasaran25/tiara-website.git
cd tiara-website

# Copy your files into the folder
# - tiara.html
# - deploy.sh
# - webhook-receiver.py
# - tiara-webhook.service
# - tiara-nginx.conf
# - DEPLOYMENT.md

# Push to GitHub
git add .
git commit -m "Initial commit: Tiara website and deployment files"
git push origin main<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Beauty Website</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>Welcome to the Beauty Website</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section id="home">
            <h2>Home</h2>
            <p>This is the home section of the beauty website.</p>
        </section>
        <section id="about">
            <h2>About Us</h2>
            <p>Learn more about our beauty services.</p>
        </section>
        <section id="services">
            <h2>Our Services</h2>
            <ul>
                <li>Makeup</li>
                <li>Skincare</li>
                <li>Hair Styling</li>
            </ul>
        </section>
        <section id="contact">
            <h2>Contact Us</h2>
            <p>Email us at: info@beautywebsite.com</p>
        </section>
    </main>
    <footer>
        <p>&copy; 2026 Beauty Website. All rights reserved.</p>
    </footer>
</body>
</html>https://github.com/tiarasaran25/Customisable-website.git
