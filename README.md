Blok - Campus Task Economy
A peer-to-peer task marketplace for our campus. Students post tasks (errands, academic help, documentation) and others accept them for monetary rewards with deadline penalties and trust scores. Fully offline - all data stored in local storage.

Features:-
1.Task Posting: Post tasks with category, deadline, reward, location (remote or campus spots), gender-sensitive flag
2.Task Discovery: Filter by remote/on-Site, sort by price
3.Smart Incentives: 50% penalty for late completion, trust score adjustments (+3/-2 points)
4.Campus-Focused: Predefined spots (Mess, Library, Canteen, etc.)
5.Mobile-First: Responsive design optimized for phone screens

Quick Demo:-
1.Enter name & accept terms → Join Blok
2."Need It" → Post "Submit assignment" for ₹50, deadline 5PM
3."On It" → Browse/accept tasks → "Accept →"
4."Profile" → Mark complete before deadline → Earn full ₹50 (+3 trust)
5.Late completion → 50% penalty applied automatically

Tech Stack:-
1.React: (hooks only - useState, useEffect, useMemo)
2.local storage: (persistent data - tasks, profile)
3.CSS-in-JS: (inline styles - zero dependencies)
4.Zero Build: Single HTML file deployment
5.Mobile Responsive: Optimized for 480px width

How It Works:-
Onboarding → Profile Created (name + trustScore:80)
   ↓
Post Task → Added to Available list (id, status:"Available")
   ↓
Accept → Status:"In Progress", assignedTo:yourName
   ↓
Complete →
On-time: +full reward, +3 trustScore
Late: +50% reward, -2 trustScore


Key Mechanics:-
1.`isLate()` checks current time vs deadline
2.Trust score: 0-100, color-coded (green≥70, yellow≥40, red)
3.Tasks auto-filter by status/location
4.Task notifications for feedback

Deployment:-
One file deployment:-
html
<!DOCTYPE html>
<html>
<head>
 <script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
 <script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
 <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
</head>
<body>
 <div id="root"></div>
 <script type="text/babel">
   // Paste entire code here
 </script>
</body>
</html>

Live Demo: [Deploy to CodeSandbox/StackBlitz](https://codesandbox.io)

Design System
| Component | Purpose | Colors |
| Primary | Buttons, accents | `#6c47ff` |
| Success| On-time completion | `#059669` |
| Warning | Late penalty | `#dc2626` |
| Background| Cards, neutral | `#f8f7f4` |

Categories:-
1.Documentation: Blue `#1e40af`
2.Academic: Purple `#5b21b6`
3.Errands: Orange `#92400e`
4.Other: Gray `#374151`

Customization:-
js
const CATEGORIES = ["Documentation", "Academic", "Errands", "Other"];
const CAMPUS_SPOTS = ["Mess", "Residency", "Library", "Canteen", "Sports Complex", "Main Gate"];

Trust score logic
trustScore: Math.min(100, p.trustScore + (late ? -2 : 3))

Penalty system
earned = late ? task.reward * 0.5 : task.reward

Development:-
# Development (CodeSandbox/StackBlitz)
1. Create React sandbox
2. Replace App.js with this code
3. Done - hot reload works

# Local dev
npx create-react-app blok
# Replace src/App.js
npm start

Contributing:-
1. Fork & create PR
2. Add your campus spots to `CAMPUS_SPOTS`
3. Test mobile view (Chrome DevTools)
4. Keep it zero-dependency

License:-
MIT - Use freely for campus projects. Credit appreciated!
Made for college students, by college students.
Deploy today - earn tomorrow. 


