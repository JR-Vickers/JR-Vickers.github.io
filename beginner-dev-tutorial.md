# From Zero to One: A Beginner's Guide to Building Software

Welcome to this comprehensive tutorial designed to take you from zero coding knowledge to deploying your first web applications. This guide is structured into two main sections:

- **1-Hour Portfolio Project**: Create and deploy a simple portfolio website using GitHub Pages
- **6-Hour Web App Project**: Build and deploy a fully functional web application

Let's begin your journey into software development!

## 1-Hour Portfolio Project

### 1. Creating a GitHub Account

GitHub is a platform where developers store and share code. It's essential for any software developer.

1. Go to [GitHub's website](https://github.com)
2. Click on "Sign up" in the top-right corner
3. Follow the registration process:
   - Enter your email address
   - Create a password
   - Choose a username
   - Solve the verification puzzle
   - Click "Create account"
4. Verify your email address by clicking the link GitHub sends you

### 2. Creating a Git Repository

A repository (or "repo") is like a project folder that stores all your code.

1. Log in to GitHub
2. Click the "+" icon in the top-right corner 
3. Select "New repository"
4. Name your repository (e.g., "my-portfolio")
5. Add a brief description (optional)
6. Make sure "Public" is selected
7. Check the box for "Add a README file"
8. Click "Create repository"

### 3. Pulling the Repository Locally

Now you'll download your repository to your computer to work on it.

First, install Git:
- **Windows**: Download and install from [git-scm.com](https://git-scm.com/download/win)
- **Mac**: Open Terminal and run `brew install git` (if you have Homebrew) or download from [git-scm.com](https://git-scm.com/download/mac)
- **Linux**: Use your package manager, e.g., `sudo apt-get install git`

Then clone your repository:

1. On your GitHub repository page, click the green "Code" button
2. Copy the HTTPS URL
3. Open a terminal (Command Prompt on Windows, Terminal on Mac/Linux)
4. Navigate to where you want to store your project: `cd Documents` (for example)
5. Run: `git clone [paste-your-repo-url-here]`
6. Enter your GitHub credentials if prompted

### 4. Using VSCode/Cursor to Open Your Project

VSCode is a popular, free code editor with many helpful features.

1. Download and install [VSCode](https://code.visualstudio.com/) or [Cursor](https://cursor.sh/)
2. Open VSCode/Cursor
3. Go to File > Open Folder
4. Navigate to and select your cloned repository folder
5. Click "Open"

Your project is now open in VSCode/Cursor!

### 5. Creating and Editing a Markdown File

Markdown is a simple formatting language that GitHub can render as a webpage.

1. In VSCode/Cursor, right-click in the Explorer sidebar
2. Select "New File"
3. Name it `index.md`
4. Add content to your markdown file. Here's a simple portfolio template:

```markdown
# Jane Doe

## About Me
Software developer passionate about creating useful applications and learning new technologies.

## Skills
- HTML/CSS
- JavaScript
- Git
- Markdown

## Projects
- **Portfolio Website**: This very website!

## Contact
- Email: jane.doe@example.com
- GitHub: [janedoe](https://github.com/janedoe)
```

5. Save the file (Ctrl+S or Cmd+S)

### 6. Upload to GitHub

Now let's send your changes back to GitHub:

1. Open the terminal in VSCode/Cursor (View > Terminal)
2. Stage your new file: `git add index.md`
3. Commit your changes: `git commit -m "Add portfolio content"`
4. Push to GitHub: `git push origin main`
5. Enter your GitHub credentials if prompted

### 7. Set Up GitHub Pages

GitHub Pages will host your markdown file as a website.

1. Go to your repository on GitHub
2. Click "Settings"
3. In the left sidebar, click "Pages"
4. Under "Source", select "Deploy from a branch"
5. Under "Branch", select "main" and "/root" folder, then click "Save"
6. Wait a few minutes for your site to deploy
7. GitHub will show you the URL of your published site (typically `https://yourusername.github.io/my-portfolio/`)

Congratulations! You've just created and deployed your first website.

## 6-Hour Web App Project

Let's create a more complex web application with modern tools and technologies.

### 1. Draw Out the UI on Excalidraw

Let's plan our application's user interface before coding.

1. Go to [Excalidraw](https://excalidraw.com/)
2. Design your web app interface. Consider:
   - Navigation bar
   - Main content area
   - Footer
   - Any special features (forms, buttons, etc.)
3. Save your design locally (File > Save to disk)
4. Create a folder called `designs` in your project and move the saved file there

### 2. Set Up a Next.js Project

Next.js is a React framework that makes building web applications easier.

First, make sure you have Node.js installed:
- Download and install from [nodejs.org](https://nodejs.org/)

Now create a Next.js project:

1. Open a terminal
2. Navigate to where you want to create your project
3. Run:
   ```bash
   npx create-next-app@latest my-web-app
   ```
4. Answer the setup questions:
   - Would you like to use TypeScript? Yes
   - Would you like to use ESLint? Yes
   - Would you like to use Tailwind CSS? Yes
   - Would you like to use `src/` directory? Yes
   - Would you like to use App Router? Yes
   - Would you like to customize the default import alias? No
5. Navigate into your project: `cd my-web-app`
6. Start the development server: `npm run dev`
7. Open your browser to `http://localhost:3000` to see your app

### 3. Use AI Tools with Copy-Paste Technique

AI tools can help you generate code snippets and solve problems.

Let's ask Claude or ChatGPT to create a simple component:

1. Prompt: "Create a React component for a navigation bar with Home, About, and Contact links using Tailwind CSS."
2. Copy the generated code
3. In VSCode/Cursor, create a new file at `src/components/Navbar.jsx`
4. Paste the code and modify as needed
5. Import and use this component in your main page

Example workflow:

1. Identify what you need to build
2. Ask an AI tool for the relevant code
3. Copy the code into your project
4. Understand and modify it to fit your needs
5. Test that it works as expected

### 4. Setting Up ShadCN Design

ShadCN provides beautiful, accessible UI components.

1. In your project directory, run:
   ```bash
   npx shadcn-ui@latest init
   ```
2. Answer the configuration questions:
   - Which style would you like to use? › Default
   - Which color would you like to use as base color? › Slate
   - Where is your global CSS file? › › src/app/globals.css
   - Do you want to use CSS variables for colors? › yes
   - Are you using a custom tailwind prefix? › No
   - Where is your tailwind.config.js located? › tailwind.config.js
   - Configure the import alias for components? › @/components
   - Configure the import alias for utils? › @/lib/utils
   - Are you using React Server Components? › yes
   - Write configuration to components.json? › yes

3. Install and use components as needed:
   ```bash
   npx shadcn-ui@latest add button
   npx shadcn-ui@latest add card
   ```

4. Use the components in your code:

```jsx
import { Button } from "@/components/ui/button";

export default function Home() {
  return (
    <div>
      <h1>Welcome to My App</h1>
      <Button>Click me</Button>
    </div>
  );
}
```

### 5. Creating a .env File

Environment variables store sensitive information like API keys.

1. In your project root, create a file named `.env.local`
2. Add your environment variables:
   ```
   NEXT_PUBLIC_APP_NAME=My Web App
   API_KEY=your_api_key_here
   ```
3. Access these variables in your code:
   ```jsx
   // This is accessible on client-side
   console.log(process.env.NEXT_PUBLIC_APP_NAME)
   
   // This is only accessible on server-side
   console.log(process.env.API_KEY)
   ```
4. Add `.env.local` to your `.gitignore` file to prevent committing sensitive data

### 6. (Optional) Set Up Supabase for Auth and Login Page

Supabase provides authentication, database, and storage services.

1. Create a Supabase account at [supabase.com](https://supabase.com/)
2. Create a new project
3. Install Supabase in your Next.js project:
   ```bash
   npm install @supabase/supabase-js
   ```
4. Create a file `src/lib/supabase.js`:
   ```javascript
   import { createClient } from '@supabase/supabase-js';

   const supabaseUrl = process.env.NEXT_PUBLIC_SUPABASE_URL;
   const supabaseAnonKey = process.env.NEXT_PUBLIC_SUPABASE_ANON_KEY;

   export const supabase = createClient(supabaseUrl, supabaseAnonKey);
   ```
5. Add Supabase credentials to your `.env.local`:
   ```
   NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

6. Create a simple login component:

```jsx
"use client";
import { useState } from 'react';
import { supabase } from '@/lib/supabase';
import { Button } from "@/components/ui/button";
import { Input } from "@/components/ui/input";

export default function Login() {
  const [email, setEmail] = useState('');
  const [password, setPassword] = useState('');
  const [loading, setLoading] = useState(false);
  const [message, setMessage] = useState('');

  const handleSignIn = async (e) => {
    e.preventDefault();
    setLoading(true);
    setMessage('');
    
    try {
      const { error } = await supabase.auth.signInWithPassword({
        email,
        password,
      });
      
      if (error) throw error;
      setMessage('Success! Redirecting...');
      window.location.href = '/dashboard';
    } catch (error) {
      setMessage(error.message);
    } finally {
      setLoading(false);
    }
  };

  return (
    <div className="max-w-md mx-auto mt-10 p-6 bg-white rounded-lg shadow-md">
      <h2 className="text-2xl font-bold mb-6">Log In</h2>
      {message && <p className="mb-4 text-center">{message}</p>}
      <form onSubmit={handleSignIn}>
        <div className="mb-4">
          <label className="block mb-2">Email</label>
          <Input
            type="email"
            value={email}
            onChange={(e) => setEmail(e.target.value)}
            required
          />
        </div>
        <div className="mb-6">
          <label className="block mb-2">Password</label>
          <Input
            type="password"
            value={password}
            onChange={(e) => setPassword(e.target.value)}
            required
          />
        </div>
        <Button type="submit" disabled={loading} className="w-full">
          {loading ? 'Loading...' : 'Log In'}
        </Button>
      </form>
    </div>
  );
}
```

### 7. Push to Vercel

Vercel makes deploying Next.js apps simple.

1. Create an account at [vercel.com](https://vercel.com/)
2. First, push your project to GitHub:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/my-web-app.git
   git push -u origin main
   ```
3. Go to Vercel dashboard
4. Click "New Project"
5. Import your GitHub repository
6. Configure your project settings (environment variables, build settings)
7. Click "Deploy"
8. Wait for the deployment to complete
9. Vercel will provide a URL for your live app

### 8. Buy a Domain from DNSimple

A custom domain looks more professional than a vercel.app subdomain.

1. Go to [dnsimple.com](https://dnsimple.com/)
2. Search for your desired domain name
3. Follow the purchase process
4. Create an account and complete payment

### 9. Set Up Domain Name on Vercel

Connect your new domain to your Vercel project.

1. Go to your Vercel project dashboard
2. Click "Settings" > "Domains"
3. Enter your domain name and click "Add"
4. Follow Vercel's instructions to:
   - Configure nameservers at your domain registrar (DNSimple)
   - Or add specific DNS records
5. Wait for DNS propagation (can take up to 48 hours, but often completes in minutes)
6. Once verified, your website will be accessible at your custom domain

## Conclusion

Congratulations! You've completed both the 1-hour portfolio project and the 6-hour web app project. You now have:

1. A simple portfolio website hosted on GitHub Pages
2. A more complex web application with:
   - Modern UI using Next.js and ShadCN
   - Authentication (if you implemented Supabase)
   - Deployment on Vercel
   - A custom domain

This is just the beginning of your software development journey. As you continue learning, you'll be able to add more features and build increasingly complex applications.

## Next Steps

- Learn more about React and Next.js
- Explore databases to store and retrieve data
- Study API development to connect your frontend with backend services
- Improve your UI/UX design skills
- Learn about testing and CI/CD pipelines

Happy coding!
