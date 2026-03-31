# RakshaCircle User Testing Instructions

Use this document to guide your 5 test users through the MVP validation session.

---

## Pre-Test Setup

### For Each User:
1. Ensure they have a **Stellar testnet account** (free from https://lab.stellar.org)
2. Ensure they have **Freighter wallet** browser extension installed
3. Share testnet XLM: ~10 XLM per user (they'll need it for transaction fees)
4. Send them the **RakshaCircle app URL** (http://localhost:5173 for local or deployed URL)

---

## Test Session Flow (15 minutes per user)

### Phase 1: Setup (2 minutes)

**Instructions to give user:**

1. Open RakshaCircle app
2. Click "Connect Freighter Wallet"
3. Approve the connection in Freighter
4. Enter your name in the profile form
5. Click "Create Profile"
6. Wait for confirmation

**What you should see:**
- "Profile created successfully"
- User's wallet address displayed
- Profile name shown on page

**Troubleshooting if stuck:**
- If Freighter not connecting: Use "Demo Wallet" fallback option
- If page won't load: Check backend is running on port 3000

---

### Phase 2: Add Trusted Contacts (2 minutes)

**Instructions to give user:**

1. On the "Trusted Contacts" section, enter contact details
2. Add at least 2 trusted contacts (use different wallet addresses)
   - Contact 1 Name: Mom, Wallet: [GIVE them test wallet from lab]
   - Contact 2 Name: Sister, Wallet: [GIVE them test wallet from lab]
3. Click "Add Contact"
4. Verify contacts appear in the list below

**What you should see:**
- Both contacts listed with their names and wallet addresses (truncated)
- "Contact added" confirmation messages

**Note to users:**
- In real scenario, contacts would be their actual emergency people
- For testing, use test wallets from https://lab.stellar.org

---

### Phase 3: Trigger SOS Alert (3 minutes)

**Instructions to give user:**

1. Scroll to "Send SOS Alert" section
2. Enter alert description: "Testing RakshaCircle SOS system"
3. Optional: Add location hint or context
4. Click "Send SOS Alert"
5. Note the **Alert ID** that appears (important!)

**What you should see:**
- SOS alert confirmed with timestamp
- Alert ID displayed
- "Alert recorded on blockchain" status message
- Timestamp showing alert creation time

**Test variation:**
- Have user trigger 2 different SOS alerts
- Notice they get different Alert IDs

---

### Phase 4: Contact Acknowledgment (4 minutes)

**Instructions to give user:**

1. Stay on the same device OR switch to another device with a test contact's wallet
2. Look at "Alert History" section
3. Find the SOS alert you just created
4. If you're the contact with wallet, click "Acknowledge"
5. Add a note: "I received your alert. I'm calling you."
6. Click "Acknowledge SOS"

**What you should see:**
- Acknowledgment confirmation
- Contact name added to acknowledgment list
- Timestamp of acknowledgment
- Alert status changes to "Acknowledged by [Name]"

**If you're testing with only one wallet:**
- Manually verify the backend received the acknowledgment
- Check via API call: `curl http://localhost:3000/api/v1/raksha/dashboard/{wallet}`

---

### Phase 5: Dashboard Review (2 minutes)

**Instructions to give user:**

1. Scroll to "Dashboard" section
2. Review statistics:
   - Total Events
   - Acknowledged Events
   - Active Events
   - Total Acknowledgments
3. Review "Recent Events" list showing all alerts

**What you should see:**
- Dashboard stats match your actions (e.g., if you created 2 alerts, Total Events = 2)
- Recent events list shows alerts in reverse chronological order
- Each event shows timestamp and status

---

### Phase 6: Feedback Collection (2 minutes)

**After completing test, ask user to fill the feedback form:**

Present these questions (can be verbal or written form):

**Q1: Setup Experience**
- Was connecting your wallet easy? (1=Very Hard, 5=Very Easy)
- Comments?

**Q2: Core Functionality**
- Did you successfully trigger an SOS alert? (Yes/No)
- Did acknowledgment work? (Yes/No)

**Q3: Blockchain Integration**
- Did you see blockchain confirmations? (Yes/No)
- Did you trust that your data was recorded securely? (1=Not at all, 5=Completely)

**Q4: UI/UX**
- Was the interface intuitive? (1=Confusing, 5=Very Clear)
- What confused you (if anything)?

**Q5: Feature Requests**
- What one feature would you add? (open answer)

**Q6: Real-World Readiness**
- Would you use RakshaCircle in a real emergency? (Yes/No/Maybe)
- Why or why not?

**Q7: Overall Rating**
- Overall experience rating: (1-5 stars)

---

## Data Collection Template

**For each test session, fill:**

```
Test Session #: [1-5]
Date: [Date]
Time Duration: [minutes]
Tester Wallet: [wallet address]
Tester Contacts: [wallet addresses added]

Setup Success: Yes / No
Alert Triggered Success: Yes / No
Acknowledgment Success: Yes / No
Dashboard Loaded: Yes / No
Blockchain Confirmed: Yes / No

Issues Encountered:
- [Issue 1]
- [Issue 2]

Feedback Provided: Yes / No
Feedback Summary:
- Setup ease: [1-5]
- Functionality works: Yes/No
- Would use in real emergency: Yes/No/Maybe
- Key improvement request: [text]

Notes:
- [Any observations]
```

---

## What to Do If Things Break

### "Freighter won't connect"
- **Solution**: Click "Use Demo Wallet" button to proceed
- **Action**: Note this in feedback as "Freighter experienced connection issues"

### "SOS alert fails to send"
- **Check**: Backend is running (`npm run dev` in terminal)
- **Check**: Frontend env var VITE_API_BASE_URL points to correct backend
- **Fallback**: Use demo wallet and try again

### "Dashboard numbers don't match"
- **Expected behavior**: Dashboard may cache for a few seconds
- **Solution**: Refresh page and wait 5 seconds
- **If persists**: Backend may have crashed, restart it

### "Contact acknowledgment button disabled"
- **Reason**: You must be using the contact's wallet to acknowledge
- **Solution**: Copy contact wallet address or ask contact person to test acknowledgment

---

## Success Criteria for Each User

User session is **successful** if:
- ✅ Profile created
- ✅ At least 2 contacts added
- ✅ SOS alert triggered
- ✅ Acknowledgment received (or verified on backend)
- ✅ Dashboard accessible
- ✅ Feedback form completed

---

## Recording Test Results

**Create a document with:**

1. **Test Summary Table**
   | User # | Date | Time | Setup OK | SOS OK | Ack OK | Dashboard | Overall |
   |--------|------|------|----------|--------|--------|-----------|---------|
   | 1      | 3/31 | 3:00 | ✓        | ✓      | ✓      | ✓         | PASS    |
   | 2      | 3/31 | 4:15 | ✓        | ✓      | ✗      | ✓         | ISSUES  |
   | ...    |      |      |          |        |        |           |         |

2. **Key Feedback Themes**
   - Setup: 4.4/5 average (easy but one user confused by Freighter)
   - Functionality: 5/5 all passed
   - Would use: 4/5 would use in real emergency

3. **Issues Found**
   - Freighter sometimes slow to respond (1 report)
   - Acknowledgment button position unclear (2 reports)
   - Backend crashed once (1 incident, recovered)

4. **Iteration Planned**
   - Add help text for acknowledgment button
   - Add "Retry" for failed SOS attempts

---

## Example: Completed Test Report

```
Date: March 31, 2026
Total Users: 5
Duration: 75 minutes (average 15 min per user)

SUCCESS RATE: 5/5 (100%)

Detailed Results:

USER 1: Priya
- Time: 3:00-3:15
- Setup: ✓ (Freighter connected first try)
- SOS: ✓ (Alert created, ID: abc123)
- Ack: ✓ (Acknowledged as contact)
- Dashboard: ✓
- Feedback: "Loved it. Very secure feeling."
- Rating: 5/5

USER 2: Anjali
- Time: 3:20-3:35
- Setup: ✓ (Used demo wallet, took 30 seconds)
- SOS: ✓
- Ack: ✓ (With help from tester)
- Dashboard: ✓
- Feedback: "Easy to use. Acknowledge button should be bigger."
- Rating: 4/5

...

AGGREGATE INSIGHTS:
- Setup: 100% success, average time 1 min
- SOS: 100% success
- Ack: 100% success
- Dashboard: 100% accessible
- Average rating: 4.6/5
- Common request: Better button labels

ITERATION IMPLEMENTED:
- Added tooltip to acknowledge button
- Changed button color to make it more prominent
```

---

## After Testing

1. **Compile results** into test report (use template above)
2. **Extract feedback themes** (3-5 key insights)
3. **Plan one iteration** based on feedback
4. **Update frontend/backend** with the iteration
5. **Document the change** for submission
6. **Take screenshots** showing the before and after

---

## Timeline Example

- **Session 1**: 3:00 PM - User A
- **Session 2**: 3:20 PM - User B
- **Session 3**: 3:40 PM - User C
- **Session 4**: 4:00 PM - User D
- **Session 5**: 4:20 PM - User E
- **Compilation**: 4:40-5:00 PM (20 min to compile results)
- **Total**: ~2.5 hours for all 5 users + report

---

**End of Testing Instructions**
