# Central Florida Kendobu Website

A modern website for Central Florida Kendobu built with SvelteKit, featuring information about the club, practice schedules, cabinet members, and contact forms.

## 🚀 Features

- **Responsive Design** - Works on desktop and mobile devices
- **Image Slideshow** - Dynamic showcase of kendo practice sessions
- **Club Information** - About section, practice schedules, and cabinet member profiles
- **Contact Form** - Integrated contact form for inquiries
- **Modern UI** - Clean, professional design with navy blue and yellow theme

## 🛠️ Tech Stack

- **Frontend**: SvelteKit + TypeScript
- **Styling**: CSS with custom components
- **Build Tool**: Vite
- **Package Manager**: npm

## 📁 Project Structure
  ```
    CFKSite/
    ├── src/
    │ ├── routes/
    │ │ ├── +layout.svelte # Main layout with header/navigation
    │ │ └── +page.svelte # Homepage with all sections
    │ └── app.html # HTML template
    ├── static/
    │ └── resources/
    │ ├── kendologo.png # Club logo
    │ ├── kendo1.jpg # Slideshow images
    │ ├── kendo2.jpg
    │ ├── kendo3.jpg
    │ ├── james.jpg # Cabinet member photos
    │ ├── eric.jpg
    │ ├── sam.jpg
    │ └── placeholder.jpg
    ├── package.json
    ├── svelte.config.js
    ├── vite.config.ts
    └── tsconfig.json
  ```
 
## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- npm

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/shadowstorm37/CFKSite.git
   cd CFKSite
   ```
   
2. **Install Dependencies**
    ```bash
    npm install
    ```

3. **Start Development Server**
    ```bash
    npm run dev
    ```
4 **Open Your Browser**
  Navigate to http://localhost:5173

### Other Scripts
  * `npm run build` - Create production build
  * `npm run preview` - Preview production build locally
  * `npm run check` - Run Svelte checks
  
## Customization

  ### Updating Content
  - **Homepage Content**: Edit `src/routes/+page.svelte`
  - **Layout/Header**: Edit `src/routes/+layout.svelte`
  - **Images**: Add to `static/resources/` and update references

  ### Updating Cabinet Members
  Edit the cabinet section in `src/routes/+page.svelte`:
  
    ```svelte
    <div class="cabinet-member">
      <img src="resources/member-photo.jpg" alt="Position">
      <div class="cabinet-title">Position</div>
      <div class="cabinet-name">Member Name</div>
      <div class="cabinet-rank">Rank</div>
    </div>
    ```

  ### Updating Slideshow Images
  Modify the `images` array in `src/routes/+page.svelte`:
  
    ```svelte
    let images: string[] = [
      "resources/your-image1.jpg",
      "resources/your-image2.jpg",
      "resources/your-image3.jpg"
    ];
    ```

  ### Color Scheme
  - **Primary Navy**: `#001f3f`/`#141414`
  - **Accent Gold**: `ffcc00`
  - **Background**: White
  - **Text**: Black/White (for contrast)

  ### Contact Form Setup
  The contact form uses EmailJS. To enable it:

  1. Create an EmailJS account
  2. Update the service ID, template ID, and user ID in `src/routes/+page.svelte`
  3. Configure your email template in EmailJS dashboard

## Deployment

  ### Build for Production
      ```bash
      npm run build
      ```
    
  ### Deploy to Static Hosting
  This site can be deployed to:
  - Vercel
  - Netlify
  - GitHub Pages
  - Any static hosting service

  ### Contributing
  1. Fork the repository
  2. Create a feature branch
  3. Commit your changes
  4. Push to the branch
  5. Create a pull request

  ### License
  All rights reserved. This project is for Central Florida Kendobu internal use.

  ### About Central Florida Kendobu
  Central Florida Kendobu was established in 2007 to introduce Kendo to students at the University of Central Florida. We provide an inclusive environment where anyone can learn Kendo regardless of experience level.

  - Practice Schedule: Every Tuesday and Thursday, 9:00 - 11:00 PM
  - Location: Group Exercise Room II, University of Central Florida

  ### Contact
  - **Email**: kendoclub@ucf.edu

