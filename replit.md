# Overview

This project is a website for 4PEXONIC INC., described as a "Scientific & Fundamental Research" organization with a tech-powered research focus. The website appears to be a modern, single-page application with a dark theme featuring scientific/tech aesthetics. The site uses custom CSS variables for consistent branding with colors like deep night blue backgrounds and tech cyan-green accents.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Static HTML/CSS/JS Structure**: Simple client-side only website with no backend dependencies
- **Single Page Application**: Built as a static site with navigation between different sections/pages
- **Responsive Design**: Uses viewport meta tags and CSS for mobile-first responsive layout
- **Modern CSS**: Utilizes CSS custom properties (variables) for consistent theming and color management

## Styling and Design System
- **Color Scheme**: Dark theme with carefully defined brand colors including deep blue backgrounds (#0A1220), tech cyan-green primary (#00E7D4), and accent blue (#7C9DFF)
- **Typography**: Dual font system using Michroma for headers/display text and Inter for body text
- **Component-Based CSS**: Organized with CSS variables for maintainable theming

## File Structure
- **Main Entry Point**: `index.html` serves as the primary page
- **Modular Assets**: Separate `style.css` and `script.js` files for organization
- **Conversation History**: Contains development conversation in `conversation.md`
- **Attached Assets**: Additional HTML versions stored in `attached_assets/` directory

## Browser Compatibility
- **Modern Standards**: Uses current HTML5, CSS3, and modern font loading techniques
- **Progressive Enhancement**: Includes fallback fonts and cross-browser font smoothing
- **SEO Optimization**: Includes proper meta tags, Open Graph properties, and semantic HTML

# External Dependencies

## Fonts
- **Google Fonts**: Loads Michroma and Inter font families via Google Fonts CDN
- **Font Display Strategy**: Uses `display=swap` for optimal loading performance

## Meta and SEO
- **Open Graph Protocol**: Integrated for social media sharing optimization
- **Favicon System**: Comprehensive favicon setup supporting multiple formats (SVG, PNG, ICO) and device types

## Browser Features
- **Modern CSS Features**: Relies on CSS custom properties, advanced selectors, and modern layout techniques
- **Font Rendering**: Uses webkit and moz font smoothing for optimal text rendering across browsers

Note: This is a purely frontend static website with no backend services, databases, or server-side processing requirements.