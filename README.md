# Heritage: keep the stories of the people you love

**Live app: [heritage-six-theta.vercel.app](https://heritage-six-theta.vercel.app)**

Heritage is a mobile-first web app for writing down family stories before they're lost. You add the people you want to remember, then capture one story at a time: a recipe, a saying, the way they took their coffee.

## The problem

Family stories mostly live in people's heads. When a grandparent or parent is gone, the small details go with them. People mean to write them down, but a blank page is hard to start, and most tools for this are either genealogy databases or generic note apps.

Heritage makes it about one person and one memory at a time, with a gentle prompt to get you started.

## What it does

- **Prompts to get you writing:** the Home screen offers one question at a time, like "What did they love to cook?" or "What phrase did they repeat all the time?" You can swap it for another, or free-write.
- **People:** add the relatives you want to remember and their relationship to you. Each person has their own page of stories.
- **Stories:** write, edit and reread stories, with reading time shown. Drafts save as you type.
- **Speak instead of type:** dictate a story and it's transcribed for you.
- **Listen back:** any story can be read aloud in a warm voice.
- **Gentle first run:** new users name one person and write a first story. They can also skip straight to Home.
- **Accounts:** email sign-up and login, password reset, and a private space for each user.
- **Installable:** it works as a home-screen app on iPhone (PWA).

## Design approach

- **Warm and editorial, not clinical:** a serif for story titles and quotes (Lora), a clean sans for the interface (Instrument Sans), a calm teal accent and friendly illustrations.
- **Built for phones first:** iOS-style layout and navigation, with a floating tab bar. Every control is at least 44px tall.
- **One design system:** colours, type, spacing and radius all come from shared tokens. It's documented in [`design-system/heritage/MASTER.md`](design-system/heritage/MASTER.md).
- **Empty and error states are designed, not left blank:** first-time screens, missing pages and expired links each have their own illustration and plain-language copy.

## How it's built

| Part | What it uses |
| --- | --- |
| Front end | React 19, TypeScript, Vite (`src/mvp`) |
| Accounts and data | Supabase: sign-in, plus `profiles`, `relatives` and `stories` tables with row-level security (`supabase/migrations`) |
| Voice | ElevenLabs speech-to-text and text-to-speech, through small serverless functions (`api/`, `server/`) |
| Hosting | Vercel |

### Run it locally

```bash
npm install
npm run dev
```

Create a `.env.local` file with your own keys first:

```
VITE_SUPABASE_URL=...
VITE_SUPABASE_PUBLISHABLE_KEY=...
ELEVENLABS_API_KEY=...
```

No keys are included in this repo.

## About

Designed and built by Daryna Volytska.
