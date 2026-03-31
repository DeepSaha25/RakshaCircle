# RakshaCircle Feedback & Iteration Template

Use this document to track user feedback and document iterations implemented.

---

## Google Form Questions

**Copy these to your Google Form (https://forms.google.com)**

### Section 1: Basic Info
- **Your Name (optional):** [Text]
- **Testing Date:** [Date]
- **Wallet Used:** [Text - can anonymize]

### Section 2: Setup Experience
- **Q1: Was connecting your wallet easy?** 
  - 1 = Very Hard, 2 = Hard, 3 = Okay, 4 = Easy, 5 = Very Easy
  - Comments: [Text box]

### Section 3: Core Functionality
- **Q2: Did you successfully trigger an SOS alert?**
  - Yes / No / Partial
  
- **Q3: Did your trusted contact receive the acknowledgment request?**
  - Yes / No / Couldn't test (only one wallet)

- **Q4: Did acknowledgment work properly?**
  - Yes / No / Partial

### Section 4: Blockchain Integration
- **Q5: Did you see confirmation that your alert was recorded on the blockchain?**
  - Yes / No / Not sure

- **Q6: Did you trust that your data was secure and permanent?**
  - 1 = Not at all, 2 = Slightly, 3 = Neutral, 4 = Quite a bit, 5 = Completely

### Section 5: UI/UX
- **Q7: Was the interface intuitive and easy to navigate?**
  - 1 = Very confusing, 2 = Confusing, 3 = Okay, 4 = Clear, 5 = Very clear
  
- **Q8: What CONFUSED you the most? (if anything)**
  - [Text box]

- **Q9: What did you like MOST about the app?**
  - [Text box]

### Section 6: Feature Requests
- **Q10: What ONE feature would make RakshaCircle better?**
  - [Text box]

### Section 7: Real-World Readiness
- **Q11: Would you use RakshaCircle in a real emergency?**
  - Yes / No / Maybe
  - Why? [Text box]

### Section 8: Overall
- **Q12: Overall rating:**
  - ⭐ (1 star) / ⭐⭐ (2) / ⭐⭐⭐ (3) / ⭐⭐⭐⭐ (4) / ⭐⭐⭐⭐⭐ (5)

- **Q13: Any other comments?**
  - [Text box]

---

## Feedback Summary Template

After collecting all 5 responses, fill this:

### 5-User Feedback Summary

**Date Range:** [from - to]  
**Total Responses:** 5/5 (100%)  
**Average Rating:** [X/5]

#### Setup Experience
- Average ease rating: [X/5]
- Common issues: [List 2-3]
- Success rate: [X/5 successful]

#### Functionality
- SOS success: [X/5 successful]
- Acknowledgment success: [X/5 successful]
- Dashboard visibility: [X/5 working]

#### Blockchain Trust
- Confirmed blockchain: [X/5 users]
- Trust score: [X/5 average]
- Common misconception: [If any]

#### UI/UX Feedback
**What confused users:**
1. [Issue 1] - [X users mentioned]
2. [Issue 2] - [X users mentioned]

**What users liked:**
1. [Feature 1] - [X users praised]
2. [Feature 2] - [X users praised]

#### Feature Requests (Priority Order)
1. **Requested Feature:** [Name]
   - Mentioned by: [X/5 users]
   - Use case: [Description]
   - Effort: Low/Medium/High
   - For MVP/Level 6?: [MVP or Level 6]

2. **Requested Feature:** [Name]
   - Mentioned by: [X/5 users]
   - Use case: [Description]
   - Effort: Low/Medium/High
   - For MVP/Level 6?: [MVP or Level 6]

#### Real-World Readiness
- Would use in emergency: [X/5 yes]
- Main blocker: [What's preventing them]
- Feature gap: [Most-mentioned missing feature]

#### Overall Assessment
**MVP-Ready?** Yes / No / With caveats  
**Recommendation:** [One line summary]

---

## Iteration Log Template

**After feedback, implement ONE iteration and document it here:**

### Iteration #1

**Date Started:** [Date]  
**Date Completed:** [Date]  
**Time Spent:** [hours]

**Feedback Trigger:**
- User feedback: [Specific feedback from form]
- # Users affected: [X/5]
- Impact: [High/Medium/Low]

**Decision Made:**
- What to change: [Specific change]
- Why this change: [Reasoning]
- What NOT to do: [Why you skipped other requests]

**Implementation Details:**

**Frontend Changes:**
- File: [Path]
- Change: [What was modified]
- Lines: [Before and after]

**Backend Changes:**
- File: [Path]
- Change: [What was modified]
- New endpoint?: Yes/No

**Deployment:**
- Time to rebuild: [X seconds]
- Time to redeploy: [X seconds]
- Breaking changes?: No

**Verification:**
- Manual test result: ✓ PASS
- Did this address feedback?: Yes
- New bugs introduced?: No

**Before/After Screenshots:**
- Screenshot 1 (before iteration): [Filename]
- Screenshot 2 (after iteration): [Filename]

---

## Example: Completed Iteration

### Iteration #1: Improve Acknowledgment Button Visibility

**Feedback Trigger:**
- User feedback: "I almost missed the acknowledge button - could it be more obvious?"
- # Users affected: 2/5
- Impact: Medium (affects UX for contacts)

**Decision Made:**
- What to change: Make acknowledge button larger and more prominent color
- Why: 40% of users couldn't easily find it
- What NOT to do: Complete redesign of alert card (too heavy for MVP)

**Implementation Details:**

**Frontend Changes:**
- File: frontend/src/pages/SubmissionMvp.tsx
- Change: 
  - Increased button size from 'md' to 'lg'
  - Changed button color from 'default' to 'destructive' (red)
  - Added icon (bell + checkmark)
  - Added hover animation
- Time: 15 minutes

**CSS Changes:**
- File: frontend/src/pages/SubmissionMvp.css
- Change: Added hover scale animation, transition effect
- Time: 10 minutes

**Verification:**
- Manual test: ✓ PASS (button now obvious on first glance)
- User feedback addressed?: Yes (visibility increased)
- New bugs?: No

**Before/After**
- Before: Small gray button at bottom of alert card
- After: Large red button with icon, bottom center

---

## Submission Checklist: Feedback & Iteration

Before submission, verify:

- [ ] Feedback form created and distributed
- [ ] All 5 users completed feedback
- [ ] Forms exported or screenshot taken
- [ ] Feedback summary document created
- [ ] At least one iteration identified from feedback
- [ ] Iteration implemented and tested
- [ ] Before/after screenshots captured
- [ ] Iteration documented in this file
- [ ] Changes committed to Git with clear message
- [ ] Changes tested and working
- [ ] No new bugs introduced by iteration

---

## How to Present This in Submission

In your submission packet, include:

1. **FEEDBACK_SUMMARY.md** (filled from template above)
2. **ITERATION_LOG.md** (filled from iteration template above)
3. **User Feedback Artifacts:**
   - Google Form responses (screenshot or PDF export)
   - Individual session notes
   - Screenshots from before/after
4. **Git commit history** showing iteration implementation

**Example submission text:**

> "We validated RakshaCircle with 5 real testnet users on March 31, 2026. Average rating was 4.6/5, and 100% of users successfully completed the core flow. Based on feedback that 40% of users had trouble finding the acknowledge button, we implemented Iteration #1: increased button prominence and added visual feedback. Before and after screenshots are included."

---

**End of Feedback Template**
