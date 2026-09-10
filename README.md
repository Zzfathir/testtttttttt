# **Kelana by Triple T**

**Team:** Ahmad Fathir, Aaron John Tan, Muhammad Abqary Nasution

**Problem Statement:** Travel Planner

**Video Presentation:** <u>[Unlisted Youtube Link]</u>

**Presentation Slides:** [Public Link]

## **1. Project Overview**

**The Problem.** State the causes as you understand them, who the stakeholders are and briefly mention what similar apps exist in the market (at least one) and why they fall short.

**Our Solution.** What it is in 3-4 sentences, then list out your feature-set

## **2. Ideation & Process**

### **2.1 Ideas We Considered**

Table of every distinct idea generated, with why each was kept or dropped, order it so that chosen ideas are listed first

| **Idea**   | **Why it was dropped / kept** |
| ---------- | ----------------------------- |
| A (Chosen) |                               |
| B (Chosen) |                               |
| C          |                               |

### **2.2 Ideation Boards**

<iframe src="https://embed.figma.com/board/HE4ALd8y3NLKg4pm0NnG5a/TripleJam?embed-host=share&node-id=0-1" width="100%" height="600" allowfullscreen></iframe>

[Open the FigJam ideation board in Figma](https://www.figma.com/board/HE4ALd8y3NLKg4pm0NnG5a/TripleJam?node-id=0-1&t=pfIDwiiFJnzen8Wu-1)

You can embed the images directly (recommended) or have links to your ideation board. Don’t feel forced to add as many diagrams as you can for “more marks”. The reviewers want to know how your team put your minds together to create your solution. It can be messy, with a lot of small dropped ideas. Add 1–2 lines under each explaining what it shows.

**IMPORTANT:** You can express this in any way you like, including but not limited to:

1. Mindmaps

2. Problem trees

3. Flowcharts

4. User flows

5. Crazy eights

6. Affinity diagrams

7. SCAMPER grids

8. Fishbone diagrams

9. 5 Whys chains

10. Any other scribbles :)

You can embed images in markdown like so:

```
![Mindmap](mindmap.png)
```

### **2.3 Mentor Consultation**

| **Date**           | **Mentor**  | **Feedback Received** | **What Was Changed** |
| ------------------ | ----------- | --------------------- | -------------------- |
| September 12, 2026 | Janelle Tan |                       |                      |
| September 10, 2026 | Faris Imran |                       |                      |

Even if you disagreed with a piece of feedback, you can say so and explain why. You will not be penalised for doing something against a mentor’s advice, it will still count as engaging with it.

## **3. Design & Prototype**

**UI Prototype:** [ <u>Public Link ]</u>

We recommend you embed or link 4–8 key screens as images, with a caption on each explaining the interaction

## **4. What Makes It Different**

List out novel features and explain briefly which each is original or what the twist is. You can have a comparison table to compare with existing solutions named in section 1 but this is completely optional.

## **5. Technical Architecture & Feasibility**

#### **Tech stack**

Kelana will be a mobile-friendly web application for planning trips, repairing disrupted activities, and recording shared memories. Our prototype will demonstrate this complete flow using one destination, a small activity dataset, and a group of up to four travelers. Solo travel will use the same flow with one participant.

| **Component**                      | **Proposed**<br>**Technology**                       | **Why we chose it**                                                                                                                                                                                         | **Expected constraints**<br>**and response**                                                                                                           |
| ---------------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Frontend**                       | React, TypeScript,<br>and Vite                       | Reusable components suit<br>itinerary cards, preference<br>forms, repair comparisons,<br>and memory galleries.<br>TypeScript helps keep data<br>consistent between<br>screens and backend<br>functions**.** | Browser camera and<br>video support varies.<br>We will support photo<br>uploads first and treat<br>short-video uploads as<br>a stretch goal.           |
| **Backend**                        | Supabase Edge<br>Functions, written<br>in TypeScript | Hosts our custom repair<br>and validation logic without<br>requiring a separately<br>maintained server.                                                                                                     | Functions have<br>execution limits. We will<br>evaluate a small set of<br>replacement activities<br>rather than search<br>every possible itinerary.    |
| **Database**                       | PostgreSQL<br>through Supabase                       | Trips, members,<br>preferences, activities, and<br>approvals have clear<br>relationships that suit a<br>relational database.                                                                                | Concurrent changes<br>could overwrite an<br>agreement. Each repair<br>will reference an<br>itinerary version and be<br>checked again before<br>saving. |
| **Authentication**<br>**& Access** | Supabase Auth<br>and Row Level<br>Security           | Identifies travelers and<br>restricts records to<br>authorized users. Private<br>spending ceilings will be<br>stored separately from<br>shared trip information.                                            | Access policies require<br>careful testing. The<br>backend will check<br>group constraints<br>without returning<br>another member’s<br>private values. |
| **Media storage**                  | Supabase Storage                                     | Stores photos separately<br>from trip records, with each<br>memory linked to its activity<br>and contributor.                                                                                               | Media consumes<br>storage and bandwidth<br>quickly. We will limit<br>upload sizes and use a<br>private storage bucket.                                 |

| **Frontend**<br>**Hosting** | Vercel | Supports Vite applications<br>and provides a shareable<br>deployment URL for<br>judging and testing. | Hobby hosting is<br>restricted to eligible<br>personal,<br>non-commercial use.<br>We will use an<br>appropriate plan if our<br>deployment falls<br>outside those<br>conditions. |
| --------------------------- | ------ | ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |

Supabase will host the database, authentication, storage, and backend functions. Vercel will host the frontend. The source code and setup instructions will be maintained in GitHub. Supabase Edge Functions, Supabase access policies, Vite hosting, Vercel plan conditions

Supabase’s Free plan currently includes a 500 MB database and 1 GB file storage, and projects can pause after one week of inactivity. We will keep the demonstration dataset small and check service availability before judging. Supabase pricing

#### **APIs and external services**

| **Component** | **Proposed**<br>**Technology** | **Why we chose it**                             | **Expected constraints**<br>**and response**                        |
| ------------- | ------------------------------ | ----------------------------------------------- | ------------------------------------------------------------------- |
| **API**       | Leafletjs API                  | free open-source API,have<br>pin point feature, | Support nearest toilets<br>or any other public<br>services pinpoint |

The core demonstration will use Supabase APIs and our own repair endpoint. Activity prices, opening hours, experience tags, and travel-time estimates will come from a manually prepared dataset for one destination.

Disruptions such as rain or a venue closure will be triggered through clearly labeled simulation controls. The prototype will not depend on live flight, booking, social-media, or weather integrations.

Ordinary authorized reads and writes can use Supabase directly. Sensitive constraint evaluation will run in backend functions; privileged credentials will remain on the server.

#### **System architecture diagram** (optional)

#### **Build plan & scope**

Explicitly tell the reviewer what you plan to build during the building phase. Narrow scope will read as realistic and feasible, not as a lack of ambition.
