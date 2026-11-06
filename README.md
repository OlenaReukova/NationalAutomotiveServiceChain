# National Automotive Service Chain

A demo website for **Bruce**, a voice assistant that books, checks, moves and cancels car service appointments. The page looks like a real service chain site, with a click-to-call button on it, so you can talk to Bruce straight from the browser.
<img width="1390" height="685" alt="Screenshot 2026-11-06 at 10 19 34" src="https://github.com/user-attachments/assets/02822ec9-3cc1-475e-a17c-05bd754bede0" />

**Live page:** https://olenareukova.github.io/NationalAutomotiveServiceChain/

<img width="1470" height="838" alt="Screenshot 2026-11-06 at 10 00 48" src="https://github.com/user-attachments/assets/7da17550-dead-4f2d-993b-e0a06c2b3869" />

## What Bruce can do

- Book a service appointment (maintenance, inspection or repairs)
- Check, reschedule and cancel an existing appointment
- Answer general questions about the services
- Speak English and German
- Pass you to a live agent when you ask (a simulated handover: Bruce announces it and ends the call)

## How to use it

1. Open the live page and click the call button.
2. Allow microphone access when your browser asks.
3. Talk to Bruce. For example: "I would like to book an appointment."
4. Bruce asks for your mobile number, licence plate and postal code. Use these test details:

| Item | Value |
|---|---|
| Mobile number | +49301234567 |
| Licence plate | BER-1024 |
| Postal code | 94105 |

The backend only knows this one test customer, so any other details are not recognised.

### Cancelling an appointment

- **On this web page:** a Keep / Cancel card opens on the page during the call. Tap a button to confirm.
- **From a phone:** Bruce texts a link to the number you call from. Stay on the line, open the link and tap a button. Text delivery depends on the SMS account, so if it does not arrive, use the web page.

Only a tap on **Cancel** cancels the appointment. Bruce's words alone never do.

## Tools used

| Part | Tool |
|---|---|
| Voice agent | Cognigy.AI AI Agent with a separate flow for each tool |
| Language model | Claude Haiku 4.5 |
| Speech to text | Deepgram Nova-3 (multilingual) |
| Text to speech | Deepgram |
| Web call widget | Cognigy click-to-call (WebRTC) widget |
| Text messages | Twilio SMS |
| Keep / Cancel card | Cognigy xApp with an Adaptive Card |
| Appointments backend | Capstone appointments API |
| Website | Plain HTML, hosted on GitHub Pages |

## How the page works

The page loads the Cognigy web call widget and connects it to the voice agent. A small script on the page opens the Keep / Cancel card in a panel during the call, and closes it when you have tapped a button or the call ends. This script is why the card shows on this page and not on other pages.

## Run it yourself

1. Download or clone this repository.
2. Open `index.html` in a browser, or turn on **Settings → Pages** in your GitHub repository to host it.
3. To use your own voice agent, replace the widget endpoint in `index.html` with the endpoint of your own Cognigy project.

## Notes

- This is a demo built for a course project. The appointments are test data.

