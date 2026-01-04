# Setup Guide

## Prerequisites
- Node.js 16+
- API Keys: Make.com, Calendly, Twilio, SendGrid, Stripe, OpenAI
- Google Cloud Project with Sheets API

## Quick Start

1. Clone repository
```
git clone https://github.com/kumarnukala05-eng/ai-lead-generator.git
cd ai-lead-generator
```

2. Install dependencies
```
npm install
```

3. Configure environment
```
cp .env.example .env
nano .env  # Add your API keys
```

4. Start backend
```
cd backend && npm run dev
```

5. Start frontend
```
cd frontend && npm run dev
```

## API Configuration

### Google Sheets
- Create Google Cloud Project
- Enable Sheets API
- Download service account JSON
- Share spreadsheet with service account email

### Calendly
- Get API key from Settings > Integrations
- Add to .env: CALENDLY_API_KEY

### Twilio
- Sign up at twilio.com
- Get Account SID, Auth Token, Phone Number
- Add to .env with TWILIO_ prefix

### SendGrid
- Create account at sendgrid.com
- Get API key
- Verify sender email

### Stripe
- Get API keys from dashboard
- Add publishable and secret keys

### OpenAI
- Get API key from platform.openai.com
- Add OPENAI_API_KEY to .env

## Make.com Workflows

Create 4 workflows:
1. Form Submission -> Save to Sheet + Send Message
2. Email Follow-ups (24h, 3d, 5d intervals)
3. Calendly Booking -> Update Sheet + Send Confirmation
4. Daily Reminders (24h and 2h before appointment)

## Deployment

### Backend (Heroku)
```
heroku create your-app
heroku config:set $(cat .env)
git push heroku main
```

### Frontend (Vercel)
```
vercel --prod
```

## Testing

```
curl -X POST http://localhost:5000/api/forms/submit \
  -H "Content-Type: application/json" \
  -d '{"name":"Test","email":"test@example.com","phone":"+919876543210","city":"Bangalore"}'
```

## Support

See README.md for more details. Good luck!
