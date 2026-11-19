ZedBiz Lens
Smart Business Intelligence for micro and small businesses in Zambia.
Tell it what happened today. The agent records it, calculates profit, shows the tax position that may apply, and prepares reports for ZRA, lenders and suppliers.
Working concept for the Zamtel-ZRA Innovation Challenge 2026
Track: Intelligent Digital Customer & Business Ecosystems
Status: proposal and prototype. This project is not evidence of approval or partnership with ZRA or Zamtel. It is not an official ZRA determination, and it is not a tax agent: it does not file returns, take payments or issue assessments. The prototype uses synthetic data only.
Table of contents
The idea
How AI makes it better
Our approach
What we will showcase
Calculations the agent performs
Technology and security
The full project (future updates)
Value, safeguards and measures
Repository layout (planned)
The idea
ZedBiz Lens is an AI business agent for micro and small businesses. The owner tells it what happened by typing, snapping a receipt or pasting a mobile-money message.
The agent records it, calculates gross and net profit, shows the tax position that may apply, and produces reports the owner can take to ZRA, a lender or a supplier.
What used to need a notebook, a calculator and an accountant now takes one message.
How AI makes it better
Task
Today (manual)
With the ZedBiz Lens agent
Recording
Notebook, memory, end-of-month guesswork.
Type, speak or snap a receipt; paste a mobile-money SMS. The agent extracts amount, item, date and category.
Gross and net profit
Hand calculation; costs easily missed.
Calculated instantly and explained in plain words.
Tax position
Unclear; rules change each Budget.
Compares turnover with current thresholds, estimates turnover tax (a range where guidance is unclear) and warns before the K800,000 VAT line.
Reports
Handwritten summaries nobody can verify.
One-tap Tax-Readiness Report and Business Health Report, each with an evidence trail.
Errors
Found at audit time.
Flags duplicates, missing days and unusual amounts for the owner to confirm.
Our approach
AI reads. Rules calculate. The owner confirms.
Step
What happens
1. Capture
Text, voice, receipt photo or pasted mobile-money SMS goes straight to the agent.
2. Understand
AI extracts and categorises each entry and asks the owner to confirm with one tap.
3. Calculate
A rules engine does the arithmetic using a dated, sourced Tax Rules Registry.
4. Report
Profit snapshot, tax position and PDF reports. Every figure links to its entries.
Why this design
A general chatbot can invent numbers. ZedBiz Lens keeps the AI to what it does best, reading messy input and explaining results, and hands every calculation to a transparent rules engine. The same inputs always give the same figures.
Tax rules live in a versioned registry with source and review date, so a Budget change is a content update, not a rebuild. The tool never claims to be an official ZRA determination.
Prototype and full product
Prototype: a rule-based parser and a category classifier trained on synthetic data, running locally.
Full product: a large language model for free-form and local-language input.
Both sit in front of the same rules engine, so the numbers stay identical.
What we will showcase
The landing page
One calm page that explains the idea in ten seconds and lets judges use it immediately.
Section
Content
Hero
Headline "Tell it what happened today. We do the rest." with a Try the agent button.
Live agent box
A chat field on the page. Judges type Sold 12 loaves K180, bought flour K420 and watch it become structured entries.
How it works
The four steps, in one row of icons.
Sample outputs
Previews of the profit snapshot and both reports.
Trust strip
"AI explains, rules calculate, you confirm." Privacy note and not-official-advice wording.
Who it helps
Owners, ZRA and Zamtel, one line each.
The working prototype
Built on synthetic data only, with extraction running on a locally trained model. The demo runs as a 90-second story.
Feature
What the judges see
1. Agent entry
Messy typed notes and pasted mobile-money SMS become clean entries with a confirm card. Receipt photo reading is a stretch goal.
2. Profit dashboard
Revenue, cost of sales, gross profit, expenses, net profit and cash position, updating live.
3. Tax position panel
Turnover against thresholds, estimated turnover tax, rules version and review date, plus an official ZRA link.
4. Ask the agent
Questions like "Why is my profit lower this week?" answered from the owner's own records.
5. Reports
Two PDFs in one tap, each showing the entries behind every number.
Demo story: a shop owner enters five messy inputs (typed notes and mobile-money messages), sees the dashboard update, opens the tax position, asks why profit dropped, and downloads both reports.
Calculations the agent performs
Every figure comes from the rules engine, never from the AI. The worked example uses synthetic figures for one month: sales K42,000, cost of goods K27,300, expenses K6,500.
Profit
Calculation
Formula
Worked example
Gross profit
Sales - cost of goods
42,000 - 27,300 = K14,700
Gross margin
Gross profit / sales
14,700 / 42,000 = 35.0%
Net profit
Gross profit - expenses
14,700 - 6,500 = K8,200
Net margin
Net profit / sales
8,200 / 42,000 = 19.5%
Break-even sales
Expenses / gross margin
6,500 / 0.35 = K18,571
Cash position
Opening cash + cash and mobile money in - cash out
From the recorded entries
Tax position
Calculation
Formula
Worked example
Turnover tax estimate
5% of turnover above K2,500 a month (K30,000 a year), up to K5 million
Range K1,975 to K2,100
VAT threshold watch
Projected annual turnover / K800,000
504,000 / 800,000 = 63%
Regime comparison
Turnover tax (5% of sales) against income tax (30% of profit)
K2,100 against K2,460; turnover tax is lower here
The tax estimate uses current ZRA bands and shows a range where published guidance is unclear. The regime comparison is for information only; the final choice rests with ZRA or an accountant.
Business insight
Calculation
What it does
Week-on-week change
Percentage change in sales, costs and profit, and the category that moved most, so the agent can explain why profit changed.
Mobile-money reconciliation
Mobile money received against recorded sales; flags the gap.
Unusual entries
Flags amounts far from the normal level for that category.
Record completeness
Complete entries as a share of all entries, plus days with no entries.
Model confidence
Below about 80% confidence in a category, the agent asks the owner instead of guessing.
Business Health Score
Out of 100 from profitability, record consistency, cash buffer and growth, with visible weights. An indicator from the owner's own records, not a credit score.
Every figure shows the entries behind it, and every tax figure shows the rule version and review date.
Technology and security
Layer
Choice
App
React progressive web app with Tailwind: one codebase for the landing page and the app.
Backend
FastAPI (Python).
Data
Supabase: Postgres, login and private file storage, with row-level security.
Extraction
Rule-based parser plus a scikit-learn category classifier trained on synthetic data.
Rules engine
Python functions and a versioned JSON Tax Rules Registry, each rule with source and review date.
Reports
ReportLab or WeasyPrint for the two PDF reports.
Security by design
Safeguard
How
AI cannot act alone
It only proposes entries. It cannot change tax rules, calculate tax or save without the owner's confirmation.
Validated output
Every extracted entry is checked against a schema (valid amount, date and category).
Data isolation
Row-level security so each user can only read their own records.
Minimum data
No TPINs, passwords, bank details or ID numbers collected.
Transport and storage
HTTPS, private storage and short-lived file links.
Consent and audit
Consent screen, delete-my-data option, and a log of each entry's source and confirmation.
Prototype
Synthetic data only, so no real business records are exposed.
The full project (future updates)
Stage
What it adds
Next
Offline-first capture that syncs later. Local-language voice entry, Bemba and Nyanja first, subject to user testing. Stock and inventory tracking.
Zamtel channels
USSD, SMS and WhatsApp-style agent for feature phones and low-data users. With consent and approval, Zamtel Kwacha statement import so mobile-money takings reconcile automatically.
ZRA alignment
Tax rules content validated by ZRA. Export compatible with Smart Invoice data. Guided steps into ZRA's own portal; ZRA stays the only place a return is filed or tax is paid.
Ecosystem
Consent-based, verifiable Business Health Score for lenders, suppliers and vendors. Accountant view for many clients. Anonymised insights for policy teams.
All integrations and partner roles are proposals that need approval from ZRA and Zamtel. None is assumed.
Value, safeguards and measures
Audience
Value
Business owners
Hours saved, and a clear view of profit and tax.
ZRA
Better-organised small-taxpayer data and a taxpayer-education channel.
Zamtel
More daily use of its network and mobile-money rails.
Safeguards
Not a tax agent: it does not file returns, take payments or issue assessments. Estimates are labelled. The owner confirms every AI entry. Minimal data, consent first, in line with Zambia's Data Protection Act, 2021.
How we will measure it
Time to log a day's sales
Share of AI entries confirmed without edit
Reports generated per active user
Before-and-after tax understanding
Targets are set after baseline testing, not promised in advance.
The aim is not to push every small business into the tax net. It is to help owners understand their position, keep better records and take the right next step where an obligation applies.
Repository layout (planned)
zedbiz-lens/
├── README.md
├── backend/            # FastAPI app, rules engine, entry parser
├── rules/              # Versioned JSON Tax Rules Registry
├── web/                # Landing page and app
└── data/               # Synthetic demo data only
ZedBiz Lens | Solution Design, 18 November 2026