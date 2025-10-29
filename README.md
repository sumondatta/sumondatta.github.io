// FILE: package.json
{
  "name": "irrigation-research-lab",
  "version": "1.0.2",
  "private": true,
  "homepage": "https://<YOUR-GITHUB-USERNAME>.github.io/irrigation-research-lab",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d dist",
    "smoke": "node ./scripts/smoke-test.js"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.14.1"
  },
  "devDependencies": {
    "@vitejs/plugin-react": "^4.0.0",
    "autoprefixer": "^10.4.14",
    "gh-pages": "^5.0.0",
    "postcss": "^8.4.23",
    "tailwindcss": "^3.4.7",
    "vite": "^5.0.0"
  }
}

// FILE: vite.config.js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  base: '/'
})

// FILE: tailwind.config.cjs
module.exports = {
  content: [
    './index.html',
    './src/**/*.{js,jsx,ts,tsx}'
  ],
  theme: {
    extend: {
      colors: {
        osu_orange: '#D35400'
      }
    }
  },
  plugins: []
}

// FILE: postcss.config.cjs
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}
  }
}

// FILE: public/index.html
<!doctype html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Irrigation Research Laboratory | Oklahoma State University</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>

// FILE: src/index.css
@tailwind base;
@tailwind components;
@tailwind utilities;

html, body, #root { height: 100%; }
.hero-image { object-fit: cover; }

// FILE: src/main.jsx
import React from 'react'
import { createRoot } from 'react-dom/client'
import { BrowserRouter } from 'react-router-dom'
import App from './App'
import './index.css'

const base = import.meta.env.BASE_URL || '/'

createRoot(document.getElementById('root')).render(
  React.createElement(React.StrictMode, null,
    React.createElement(BrowserRouter, { basename: base },
      React.createElement(App)
    )
  )
)

// FILE: src/App.jsx
import React from 'react'
import { Routes, Route } from 'react-router-dom'
import Navbar from './components/Navbar'
import Footer from './components/Footer'
import Home from './pages/Home'
import People from './pages/People'
import Research from './pages/Research'
import Publications from './pages/Publications'
import Projects from './pages/Projects'
import News from './pages/News'
import Contact from './pages/Contact'
import OpenPositions from './pages/OpenPositions'

export default function App(){
  return (
    <div className="min-h-screen flex flex-col bg-white text-gray-900">
      <Navbar />
      <main className="flex-grow">
        <Routes>
          <Route path="/" element={<Home/>} />
          <Route path="/people" element={<People/>} />
          <Route path="/research" element={<Research/>} />
          <Route path="/publications" element={<Publications/>} />
          <Route path="/projects" element={<Projects/>} />
          <Route path="/news" element={<News/>} />
          <Route path="/contact" element={<Contact/>} />
          <Route path="/positions" element={<OpenPositions/>} />
        </Routes>
      </main>
      <Footer />
    </div>
  )
}

// FILE: src/components/Navbar.jsx
import React from 'react'
import { Link, NavLink } from 'react-router-dom'

const NavItem = ({to, children}) => (
  <NavLink
    to={to}
    className={({isActive}) => 'px-3 py-2 rounded-md text-sm font-medium ' + (isActive ? 'bg-black text-white' : 'text-gray-700 hover:bg-gray-100')}
  >{children}</NavLink>
)

export default function Navbar(){
  return (
    <header className="shadow-sm">
      <div className="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
        <Link to="/" className="flex items-center gap-3">
          <div className="w-10 h-10 rounded-md bg-osu_orange flex items-center justify-center text-white font-bold">IR</div>
          <div>
            <h1 className="text-lg font-semibold">Irrigation Research Laboratory</h1>
            <div className="text-xs text-gray-600">Oklahoma State University</div>
          </div>
        </Link>
        <nav className="hidden md:flex items-center gap-2">
          <NavItem to="/">Home</NavItem>
          <NavItem to="/people">People</NavItem>
          <NavItem to="/research">Research</NavItem>
          <NavItem to="/projects">Projects</NavItem>
          <NavItem to="/publications">Publications</NavItem>
          <NavItem to="/news">News</NavItem>
          <NavItem to="/positions">Open Positions</NavItem>
          <NavItem to="/contact">Contact</NavItem>
        </nav>
      </div>
    </header>
  )
}

// FILE: src/components/Footer.jsx
import React from 'react'

export default function Footer(){
  return (
    <footer className="border-t mt-8">
      <div className="max-w-6xl mx-auto px-4 py-6 flex flex-col md:flex-row items-start md:items-center justify-between gap-4">
        <div>
          <div className="font-semibold">Irrigation Research Laboratory</div>
          <div className="text-sm text-gray-600">Oklahoma State University</div>
        </div>
        <div className="text-sm text-gray-600">© {new Date().getFullYear()} Oklahoma State University</div>
      </div>
    </footer>
  )
}

// FILE: src/pages/Home.jsx
import React from 'react'

export default function Home(){
  return (
    <section className="py-16">
      <div className="max-w-5xl mx-auto px-4 text-center">
        <h2 className="text-4xl font-extrabold text-osu_orange">Irrigation Research Laboratory</h2>
        <p className="mt-3 text-lg">Oklahoma State University</p>
        <p className="mt-6 text-base leading-relaxed">The Irrigation Research Laboratory at Oklahoma State University advances sustainable irrigation management through field-based experimentation, sensor integration, and data-driven modeling. Our mission is to develop decision-support tools that optimize water use efficiency, improve crop resilience, and promote climate-smart agricultural practices in the Southern Great Plains.</p>

        <div className="mt-8 grid grid-cols-1 md:grid-cols-3 gap-6">
          <div className="p-6 border rounded-lg">
            <h3 className="font-semibold">Research</h3>
            <p className="text-sm text-gray-600 mt-2">Field trials, sensor networks, irrigation scheduling, and model development.</p>
          </div>
          <div className="p-6 border rounded-lg">
            <h3 className="font-semibold">Publications</h3>
            <p className="text-sm text-gray-600 mt-2">Peer-reviewed papers, reports, and open-source tools.</p>
          </div>
          <div className="p-6 border rounded-lg">
            <h3 className="font-semibold">Opportunities</h3>
            <p className="text-sm text-gray-600 mt-2">Graduate student positions, postdocs, and collaborations.</p>
          </div>
        </div>
      </div>
    </section>
  )
}

// FILE: src/pages/People.jsx
import React from 'react'
import people from '../data/people'

export default function People(){
  return (
    <section className="py-12">
      <div className="max-w-6xl mx-auto px-4">
        <h2 className="text-2xl font-bold">People</h2>
        <p className="text-sm text-gray-600 mt-2">PI, students, and collaborators.</p>

        <div className="mt-6 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
          {people.map((p) => (
            <div key={p.email} className="border rounded-lg p-4">
              <div className="h-36 bg-gray-100 rounded-md flex items-center justify-center text-gray-400">Photo</div>
              <div className="mt-3">
                <div className="font-semibold">{p.name}</div>
                <div className="text-sm text-gray-600">{p.title}</div>
                <div className="text-sm mt-2">{p.email}</div>
              </div>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}

// FILE: src/pages/Research.jsx
import React from 'react'

export default function Research(){
  return (
    <section className="py-12">
      <div className="max-w-6xl mx-auto px-4">
        <h2 className="text-2xl font-bold">Research</h2>
        <p className="mt-2 text-gray-600">We integrate field experiments, sensor networks, remote sensing, and decision support systems to improve irrigation efficiency.</p>

        <div className="mt-6 space-y-4">
          <article className="p-4 border rounded">
            <h3 className="font-semibold">Irrigation Scheduling Tools</h3>
            <p className="text-sm text-gray-600 mt-1">Development and testing of scheduling algorithms using in-situ sensors and satellite-derived soil moisture.</p>
          </article>

          <article className="p-4 border rounded">
            <h3 className="font-semibold">Field Trials</h3>
            <p className="text-sm text-gray-600 mt-1">Long-term experiments comparing furrow, sprinkler, and subsurface drip systems under differing climate and management.</p>
          </article>
        </div>
      </div>
    </section>
  )
}

// FILE: src/pages/Publications.jsx
import React from 'react'
import publications from '../data/publications'

export default function Publications(){
  return (
    <section className="py-12">
      <div className="max-w-6xl mx-auto px-4">
        <h2 className="text-2xl font-bold">Publications</h2>
        <p className="text-sm text-gray-600 mt-2">Selected peer-reviewed papers and reports.</p>

        <ul className="mt-4 space-y-3">
          {publications.map((pub, idx) => (
            <li key={idx} className="border p-3 rounded">
              <div className="font-semibold">{pub.title}</div>
              <div className="text-sm text-gray-600">{pub.authors} — {pub.year}</div>
              <div className="mt-2 text-sm">{pub.journal}</div>
            </li>
          ))}
        </ul>
      </div>
    </section>
  )
}

// FILE: src/pages/Projects.jsx
import React from 'react'
import projects from '../data/projects'

export default function Projects(){
  return (
    <section className="py-12">
      <div className="max-w-6xl mx-auto px-4">
        <h2 className="text-2xl font-bold">Projects</h2>
        <div className="mt-6 grid grid-cols-1 md:grid-cols-2 gap-6">
          {projects.map((proj, i) => (
            <div key={i} className="border p-4 rounded">
              <div className="font-semibold">{proj.title}</div>
              <div className="text-sm text-gray-600 mt-1">{proj.summary}</div>
            </div>
          ))}
        </div>
      </div>
    </section>
  )
}

// FILE: src/pages/News.jsx
import React from 'react'

export default function News(){
  return (
    <section className="py-12">
      <div className="max-w-6xl mx-auto px-4">
        <h2 className="text-2xl font-bold">News & Updates</h2>
        <p className="text-sm text-gray-600 mt-2">Lab announcements and recent activities.</p>

        <div className="mt-6 space-y-4">
          <article className="p-4 border rounded">
            <div className="text-sm text-gray-600">Oct 2025</div>
            <h3 className="font-semibold">Lab website launched</h3>
            <p className="text-sm mt-1">Initial launch of the Irrigation Research Laboratory website and project pages.</p>
          </article>
        </div>
      </div>
    </section>
  )
}

// FILE: src/pages/Contact.jsx
import React from 'react'

export default function Contact(){
  return (
    <section className="py-12">
      <div className="max-w-3xl mx-auto px-4">
        <h2 className="text-2xl font-bold">Contact</h2>
        <p className="text-sm text-gray-600 mt-2">For inquiries, collaboration, or student opportunities, contact:</p>

        <div className="mt-4 border p-4 rounded">
          <div className="font-semibold">Dr. [PI Name]</div>
          <div className="text-sm text-gray-600">Assistant Professor, Biosystems and Agricultural Engineering</div>
          <div className="text-sm mt-2">Email: pi@example.edu</div>
        </div>
      </div>
    </section>
  )
}

// FILE: src/pages/OpenPositions.jsx
import React from 'react'

export default function OpenPositions(){
  return (
    <section className="py-12">
      <div className="max-w-4xl mx-auto px-4">
        <h2 className="text-2xl font-bold">Open Positions</h2>
        <p className="mt-2 text-gray-600">We welcome motivated graduate students and postdocs. Please email your CV and statement of interest.</p>

        <div className="mt-6 space-y-4">
          <div className="border p-4 rounded">
            <div className="font-semibold">Ph.D. Student — Irrigation & Sensor Networks</div>
            <div className="text-sm text-gray-600 mt-1">Start: Fall 2026. Funding available.</div>
          </div>
        </div>
      </div>
    </section>
  )
}

// FILE: src/data/people.js
const people = [
  { name: 'Dr. [PI Name]', title: 'Principal Investigator', email: 'pi@example.edu' },
  { name: 'Student A', title: 'Ph.D. Student', email: 'studenta@example.edu' },
  { name: 'Collaborator B', title: 'Extension Specialist', email: 'collab@example.edu' }
]
export default people

// FILE: src/data/publications.js
const publications = [
  { title: 'Scheduling irrigations with sensor-driven models', authors: 'Datta, S.; Smith, J.', year: 2024, journal: 'Agricultural Water Management' },
  { title: 'OASIS tool: An explainable irrigation advisor', authors: 'Datta, S.; Lee, K.', year: 2025, journal: 'Computers and Electronics in Agriculture' }
]
export default publications

// FILE: src/data/projects.js
const projects = [
  { title: 'OASIS Irrigation Advisor', summary: 'Evaluate and improve the OASIS scheduling tool under furrow and subsurface drip systems.' },
  { title: 'Soil sensor network deployment', summary: 'Deploy long-term soil moisture sensors across OSU research fields.' }
]
export default projects

// FILE: scripts/smoke-test.js
const { execSync } = require('child_process')
try {
  console.log('Node version:', process.version)
  const npmVersion = execSync('npm --version').toString().trim()
  console.log('npm version:', npmVersion)
  console.log('If you run into "Unexpected token" errors when starting Vite, make sure:')
  console.log(' 1) You installed dependencies (npm install)')
  console.log(' 2) @vitejs/plugin-react is present in devDependencies')
  console.log(' 3) Files using JSX have the .jsx extension or you have TypeScript configured for .tsx')
  process.exit(0)
} catch (err) {
  console.error('Smoke test failed (make sure npm is available). Error:', err.message)
  process.exit(2)
}
