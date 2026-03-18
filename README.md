# Demo AI Chatbot

A simple, scalable, and modern Next.js AI chatbot that uses OpenAI's GPT models as the intelligence engine and a Google Doc as the knowledge base. This project is designed purely as a demonstration of building domain-specific client chatbots.

## Features
- **Frontend**: Next.js Pages router with a highly polished Tailwind CSS UI (glassmorphism, gradients, micro-animations, and status indicators).
- **Backend API**: A secure Next.js API route connecting the frontend, the knowledge base, and OpenAI.
- **Knowledge Base**: Fetches context dynamically from a public Google Doc **AND/OR** a Google Sheet.
- **OpenAI Integration**: Configured to use `gpt-4o-mini` for fast, intelligent, and context-aware responses.

---

## 1. Google Docs / Sheets Knowledge Base Connection
To give the AI context about your client or product:

### Option A: Google Docs
1. Create a new [Google Doc](https://docs.google.com/).
2. Write the knowledge you want the chatbot to know (e.g., FAQs, pricing, hours of operation).
3. Click **Share** in the top right corner.
4. Under "General access," change it from "Restricted" to **"Anyone with the link"** (Viewer mode).
5. Copy the long ID from the URL: `https://docs.google.com/document/d/[GOOGLE_DOC_ID]/edit`.

### Option B: Google Sheets
1. Create a [Google Sheet](https://sheets.google.com/).
2. Organize your data (e.g., Column A: Question, Column B: Answer).
3. Click **Share** -> **Anyone with the link** (Viewer).
4. Copy the ID from the URL: `https://docs.google.com/spreadsheets/d/[GOOGLE_SHEET_ID]/edit`.

---

## 2. OpenAI API Connection
1. Go to [OpenAI Platform](https://platform.openai.com/).
2. Create a new Secret Key. This is your `OPENAI_API_KEY`.

---

## 3. Deployment on GitHub
To deploy the code easily, it needs to be pushed to GitHub:
1. Initialize a Git repository locally in the `chatbot-demo` directory:
   ```bash
   git init
   git add .
   git commit -m "Initial commit of Demo AI Chatbot"
   ```
2. Go to [GitHub](https://github.com/) and create a new repository (e.g., `ai-chatbot-demo`).
3. Follow the instructions to push your local repository to GitHub:
   ```bash
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/ai-chatbot-demo.git
   git push -u origin main
   ```

---

## 4. Deployment on Vercel
Vercel is the easiest way to deploy Next.js apps to the public web.
1. Sign up or log into [Vercel](https://vercel.com/) using your GitHub account.
2. Click **Add New** -> **Project**.
3. Import the `ai-chatbot-demo` repository you just created.
4. In the **Environment Variables** section during setup, add:
   - **Key**: `OPENAI_API_KEY`   | **Value**: `<Your OpenAI Key>`
   - **Key**: `GOOGLE_DOC_ID`    | **Value**: `<Your Google Doc ID>` (Optional)
   - **Key**: `GOOGLE_SHEET_ID`  | **Value**: `<Your Google Sheet ID>` (Optional)
5. Click **Deploy**.
6. Wait 1-2 minutes for Vercel to build. Once complete, you'll have a public URL to share!

---

## Running Locally

To run the application locally on your computer:

1. Create a `.env.local` file in the root of the project.
2. Add your environment variables:
   ```env
   OPENROUTER_API_KEY=your_key_here
   OPENROUTER_MODEL=openai/gpt-4o-mini
   GOOGLE_DOC_ID=your_id_here
   GOOGLE_SHEET_ID=your_id_here
   ```
3. Run the development server:
   ```bash
   npm run dev
   ```
4. Open [http://localhost:3000](http://localhost:3000) in your browser.
