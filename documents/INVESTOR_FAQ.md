# AskShruti! - Investor FAQ & Pitch Talking Points

## Executive Talking Points

### The Hook (30 seconds)
*"Imagine your 72-year-old grandmother trying to fill a medical form online. Complex fields, English text, small buttons. She gives up. Now imagine her speaking to AskShruti in Hindi, and watching the entire form auto-fill in 30 seconds. That's what we're building—healthcare accessibility for 500 million Indians."*

### The Problem (1 minute)
*"eSanjeevani is India's flagship telemedicine platform, and it's brilliant. But there's a critical barrier: the digital intake form. For elderly citizens, those with low literacy, and non-English speakers—which is most of India—this form is an impossible hurdle. We see 40-50% form abandonment in these demographics. The result? Millions skip healthcare simply because they can't navigate a form. This isn't a tech problem anymore—it's a healthcare access crisis."*

### The Solution (1 minute)
*"AskShruti transforms form-filling from a 10-minute struggle into a 30-second conversation. The patient simply talks to our AI assistant in Hindi about their symptoms, medical history, medications, and allergies. The AI understands medical terminology, extracts structured data, and auto-populates the entire eSanjeevani form. The patient reviews it once, and it's done. No typing, no confusion, no English, no digital literacy required."*

### Why Now? Why Us? (1 minute)
*"Three things align perfectly right now:

First, the technology is ready. Speech-to-text accuracy has hit 99%, LLMs can understand medical terminology in Hindi, and real-time processing is cheap and fast.

Second, the government moment is here. The Digital Health Mission is pushing eSanjeevani nationally, and accessibility is now a compliance requirement. They're looking for exactly this solution.

Third, the demographic urgency is clear. India's elderly population is 135 million and growing. The digital divide is widening. This is the last-mile problem that nobody's solving.

We're building this at the exact moment it becomes both possible and essential."*

### The Market Opportunity (30 seconds)
*"500 million Indians lack adequate healthcare access. Our initial target: 50 million elderly and low-literacy citizens on eSanjeevani alone. The government processes 100,000 cases daily—if we capture just 10%, that's 10,000 cases per day. At ₹20-40 per case, that's ₹200-400 crores annually from a single platform. And we're extensible to all Indian telemedicine platforms. This is a ₹500 crore+ market opportunity."*

---

## Investor FAQ

### 1. Why Voice? Why Not Just Better UX?
**Q**: Can't you just redesign the form to be more accessible?

**A**: Good question. Yes, better UX helps, but form-filling requires cognitive load—reading, understanding, typing, remembering medical details. Voice eliminates this entirely. A 70-year-old can describe their symptoms naturally, but filling a form remains a barrier even with perfect UX. Voice is 20x faster (30 seconds vs. 10 minutes) because it's conversational, not form-based.

---

### 2. Transcription Accuracy Risk
**Q**: What if Hindi transcription accuracy isn't good enough?

**A**: 
- AWS Transcribe Medical achieves 97-99% accuracy on Hindi
- Medical terminology is actually easier to recognize (not casual speech)
- We have a human verification layer—patient reviews everything before submission
- Our entity extraction (LLM-based) is robust to minor transcription errors
- We're adding confidence scoring—if confidence is low, we ask for clarification
- Worst case: Patient uses manual fallback (still faster than traditional form)

---

### 3. Entity Extraction Errors
**Q**: What if the AI misunderstands "Amlodipine" as something else?

**A**: 
- LLM confidence scoring alerts us to ambiguities
- Patient sees the extracted data in the review step
- If wrong, patient simply corrects via voice or manual edit
- Medical terminology databases help with medication names
- Few-shot prompting with Indian medical examples improves accuracy
- We target >90% first-pass accuracy, which is excellent for this use case

---

### 4. Privacy & Compliance
**Q**: Is this HIPAA compliant? Can you handle patient data?

**A**: 
- Audio deleted immediately after transcription (no permanent storage)
- All data encrypted in transit (TLS 1.3) and at rest (AES-256)
- We don't store medical data—eSanjeevani does
- We're designing for HIPAA compliance from day one
- Regular security audits and compliance certifications in roadmap
- Privacy by design: minimal data collection, minimal retention

---

### 5. Language Limitation
**Q**: Hindi is only 40% of India. What about Tamil, Telugu, Marathi?

**A**: 
- MVP launches with Hindi + English (covers 70%+ of users)
- Architecture is language-agnostic
- Adding new languages requires:
  - Speech-to-text model (AWS Transcribe supports these)
  - Few medical examples for LLM prompt (easy to add)
  - No code changes needed
- Each language adds <₹5L to development cost
- By Year 2, we target 5+ languages
- Long-term vision: All Indian languages

---

### 6. Competitive Risk
**Q**: Won't Microsoft, Amazon, or other cloud providers build this?

**A**: 
- They could, but they won't (not in their roadmap)
- We have first-mover advantage in India's healthcare space
- Our focus is vernacular + medical + elderly-first (not generic)
- Government relationship advantage (we're purpose-built for eSanjeevani)
- Difficult to compete on privacy + regulatory compliance (our focus)
- Once we're integrated into eSanjeevani, we have network effects
- Our defensible moat: healthcare domain expertise + government backing

---

### 7. Adoption & Network Effects
**Q**: Will patients and doctors actually adopt this?

**A**: 
- For patients: It's 20x faster and requires no digital literacy
- For doctors: They get structured, complete data (huge improvement)
- For eSanjeevani: It increases case completion rates
- Government has adoption incentive (accessibility mandate)
- Network effects: As more patients use it, doctors expect it
- Adoption path: Pilot with early adopters → word-of-mouth → government mandate

---

### 8. Business Model & Revenue
**Q**: How do you make money?

**A**: Multiple models possible:

1. **B2B SaaS** (Government licensing)
   - License to eSanjeevani annual payment
   - ₹5-10 Cr/year per state

2. **Per-Transaction** (Most likely)
   - Government pays ₹20-40 per completed case
   - 10M cases/year × ₹30 = ₹30 Cr revenue

3. **Platform Licensing**
   - All Indian telemedicine platforms (Practo, etc.)
   - ₹50+ Cr/year potential

4. **Freemium** (Optional)
   - Free for patients
   - Premium analytics/features for hospitals
   - Revenue from providers, not patients

Most likely: Government per-transaction model (proven, sustainable, massive scale)

---

### 9. Team & Execution Risk
**Q**: Can this team execute in 3 months?

**A**: 
- MVP is well-scoped (12 requirements document ready)
- Technology stack proven (no experimental tech)
- MVP doesn't require:
  - Scaling to millions
  - All 10 Indian languages
  - Perfect accuracy (85% is MVP target)
  - Full compliance (roadmap item)
- 3-month timeline realistic for:
  - React chatbot widget
  - Speech-to-text integration
  - LLM entity extraction
  - Form mapper + eSanjeevani API integration
- We have tech leads experienced in healthcare IT

---

### 10. Path to Profitability
**Q**: When does this become profitable?

**A**: 
- MVP cost: ₹75L (6 months)
- Pilot cost: ₹50L (2 months)
- Total pre-revenue: ₹125L
- At ₹30 per case, 1000 cases/day = ₹1 Cr/month
- Breakeven at 50,000 cases (5 days at full scale)
- Government pilot likely reaches this in Month 9-10
- Profitable by Month 12-15 (18 months from funding)

---

### 11. Regulatory & Government Risk
**Q**: What if the government doesn't support this?

**A**: 
- Low risk: Digital health is government priority
- Accessibility is compliance requirement (they need solutions)
- eSanjeevani team has been receptive in conversations
- Alternative paths: Other platforms (Practo, Apollo), private hospitals
- But government adoption is highest-value path (scale + sustainability)

---

### 12. Scaling Challenges
**Q**: How do you scale from 1000 users to 1M users?

**A**: 
- Architecture is cloud-native (auto-scaling)
- APIs cost (AWS Transcribe Medical, OpenAI) scale linearly
- Infrastructure costs: ₹50L → ₹5Cr annually (manageable)
- LLM latency: 2 seconds now, can optimize
- No custom hardware needed (cloud-based)
- Main scaling needs: More backend servers (easy to add)

---

### 13. Data Security & Breach Risk
**Q**: What's your data breach contingency?

**A**: 
- We minimize data stored (audio not stored)
- Encryption at rest + in transit (reduces breach impact)
- Regular security audits
- Cyber insurance
- Incident response plan
- GDPR-level data protection practices
- Patient data ultimately stored by eSanjeevani (their liability)

---

### 14. Accuracy Improvement Path
**Q**: How do you improve accuracy post-launch?

**A**: 
- Collect anonymized conversation data
- A/B test different prompts with LLMs
- Improve medical terminology database
- User feedback loop (what errors matter most)
- Monthly accuracy audits
- Quarterly model updates
- By Month 12: >95% accuracy target

---

### 15. Exit Strategy
**Q**: What's the exit scenario?

**A**: 
- **Acquisition path**: Healthcare IT giants (HexaHealth, Practo, OYO Health, etc.)
- **IPO path**: Become major digital health player
- **Partnership path**: Government contract could lead to larger partnerships
- **Timeline**: 5-7 year path to exit (Series A → Series B → Exit)
- **Valuation trajectory**:
  - Year 1: ₹10 Cr (50M users, ₹1Cr revenue)
  - Year 3: ₹100 Cr (5M users, ₹50Cr revenue)
  - Year 5: ₹500 Cr (healthcare scale)

---

## Key Statistics for Your Pitch

### Market Numbers
- **500M+** underserved population in India
- **135M+** elderly citizens (age 60+)
- **350M+** low-digital-literacy citizens
- **100K+** daily cases on eSanjeevani
- **40-50%** form abandonment rate (elderly users)
- **10 min** → traditional form time
- **30 sec** → AskShruti time (20x improvement)

### Technology Numbers
- **97-99%** speech recognition accuracy (AWS Transcribe Medical)
- **90-95%** entity extraction accuracy (GPT-4)
- **85-90%** form population success rate (MVP target)
- **<5 sec** end-to-end processing latency
- **₹0.44** per 15 min audio (transcription cost)
- **₹0.03-0.15** per 1K tokens (entity extraction cost)

### Business Numbers
- **₹75L** MVP development cost
- **₹20-40** per case revenue (government model)
- **10,000** cases/day (at scale)
- **₹200-400 Cr** annual revenue potential
- **₹500 Cr+** addressable market

### Timeline
- **Month 1-3** MVP development
- **Month 4-6** Pilot (1000 users)
- **Month 7-9** Government expansion (10,000 users)
- **Month 10-12** Scale & language expansion (100,000 users)
- **Year 2** ₹30-50 Cr revenue target
- **Year 3** ₹100+ Cr revenue target

---

## Presentation Closing Lines

### Strong Finish (1 minute)

*"Healthcare accessibility isn't a technology problem anymore—it's a solved problem. The barrier now is usability. AskShruti solves the last-mile problem that affects 500 million Indians right now.

We're not building a feature. We're building a platform that makes digital healthcare truly inclusive.

The government is ready. The technology is ready. The market is massive. What's missing is execution.

We're asking for ₹75 lakhs to build the MVP in 3 months. By Month 6, we'll have proven the model with 1000 users. By Month 12, we'll be processing 10,000 cases daily with 50+ million potential users.

This is a moonshot that's actually feasible. Let's make it happen."*

---

## Red Flags to Address Proactively

### If Investor Asks: "This seems too ambitious"
**Response**: "We're not building a generic translation tool. We're integrating proven APIs (AWS Transcribe Medical, GPT-4) with a well-designed workflow. MVP doesn't require perfection—85% accuracy is enough for patients to verify. We're solving an implementation problem, not a research problem."

### If Investor Asks: "Why hasn't anyone done this yet?"
**Response**: "Because it requires three things to align: (1) Speech-to-text at 99% accuracy (very recent), (2) LLMs that understand medical Hindi (last 12 months), (3) Government digital health infrastructure (eSanjeevani). All three are NOW available. This is 2024—the timing is perfect."

### If Investor Asks: "What if the government says no?"
**Response**: "Low probability, but we have Plan B: (1) Other platforms (Practo, Apollo, etc.), (2) Private hospitals, (3) Insurance companies, (4) International markets. eSanjeevani is ideal, but not essential. The problem exists everywhere."

### If Investor Asks: "Isn't this a feature, not a product?"
**Response**: "Today, yes—it's a feature in eSanjeevani. But once we prove it works, it becomes a platform: (1) All healthcare forms across platforms, (2) All Indian languages, (3) Value-added services (medication reminders, follow-ups, etc.). By Year 2, it's a standalone business."

---

## Questions to Prepare Answers For

1. What's your technical proof-of-concept?
2. Do you have eSanjeevani buy-in?
3. What about competitors?
4. How will you acquire users?
5. What's your unit economics?
6. How do you handle data privacy?
7. What's your go-to-market strategy?
8. How will you attract healthcare professionals?
9. What's your pricing strategy?
10. How will you scale internationally?

---

## Materials Checklist for Pitch

- [ ] Slide deck (15-20 slides)
- [ ] 2-minute video demo (voice → form auto-fill)
- [ ] Technical architecture diagram (printed)
- [ ] Market size validation (research/sources)
- [ ] Design documents (hardcopy for questions)
- [ ] Financial projections (5-year)
- [ ] Team bios (with credentials)
- [ ] Testimonials from domain experts
- [ ] Competition analysis slide
- [ ] Risk mitigation matrix
- [ ] One-pager (executive summary)
- [ ] FAQ document (this file)

---

## Final Positioning

**AskShruti is to digital health what mobile was to banking.**

Just like mobile made banking accessible to millions without bank accounts, AskShruti makes digital healthcare accessible to millions without digital literacy.

This is a platform moment. Let's build it together.
