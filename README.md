# Portfolio Website v1

A beautiful portfolio website built with Vue 3, Vite, and Tailwind CSS.

## 🚀 Features

- **Responsive**: Works perfectly on all devices
- **Smooth Animations**: AOS (Animate On Scroll) for beautiful transitions
- **Vue 3**: Latest Vue.js with Composition API
- **Tailwind CSS**: Utility-first CSS framework
- **Vite**: Fast build tool and dev server

## 🎨 Color Palette

- **Navy**: `#0a192f`
- **Light Navy**: `#112240`
- **Lightest Navy**: `#233554`
- **Slate**: `#8892b0`
- **Light Slate**: `#a8b2d1`
- **Lightest Slate**: `#ccd6f6`
- **White**: `#e6f1ff`
- **Green**: `#64ffda`

## 📦 Installation

1. Clone the repository
```bash
git clone https://github.com/RahimjonovBoburjon/portfolio-website.git
cd portfolio-website
```

2. Install dependencies
```bash
npm install
```

3. Start development server
```bash
npm run dev
```

4. Build for production
```bash
npm run build
```

## 🛠️ Customization

### Personal Information
Update the following in `src/App.vue`:
- Your name in the hero section
- About section content
- Experience details
- Project information
- Contact details

### Styling
- Colors are defined in `tailwind.config.js`
- Custom styles in `src/assets/main.css`
- Component-specific styles in each Vue component

### Adding Projects
1. Duplicate the project card structure in the Work section
2. Update project title, description, and technologies
3. Add your project links

## 📁 Project Structure

```
portfolio-website-v1/
├── public/
├── src/
│   ├── assets/
│   │   └── main.css
│   ├── components/
│   │   └── App.vue
│   └── main.js
├── index.html
├── package.json
├── tailwind.config.js
├── vite.config.js
└── README.md
```

## 🎯 Sections

1. **Hero**: Introduction and call-to-action
2. **About**: Personal information and skills
3. **Experience**: Work history and achievements
4. **Work**: Featured projects showcase
5. **Contact**: Get in touch section

## 🔧 Technologies Used

- **Vue 3**: Progressive JavaScript framework
- **Vite**: Next generation frontend tooling
- **Tailwind CSS**: Utility-first CSS framework
- **AOS**: Animate On Scroll library
- **Lucide Icons**: Beautiful icon library

## 📱 Responsive Design

The website is fully responsive and optimized for:
- Desktop (1200px+)
- Tablet (768px - 1199px)
- Mobile (320px - 767px)

## 🚀 Deployment

### Netlify (Recommended)
1. Connect your GitHub repository
2. Build command: `npm run build`
3. Publish directory: `dist`

### Vercel
1. Import your GitHub repository
2. Framework preset: Vue.js
3. Build command: `npm run build`

## 📄 License

MIT License - feel free to use this template for your own portfolio!