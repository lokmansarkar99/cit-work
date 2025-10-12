
# Nasscorp Agency Landing Page

A professional, modern, and fully responsive multi-section landing page designed for a business consulting or marketing agency named 'Nasscorp'.


##  Live Preview

[**Nasscorp Live Preview**](https://www.google.com/search?q=https://%5BYOUR_HOSTED_PROJECT_URL%5D)

## ✨ Overview & Features


##  Overview

This project is a single-page marketing website built using clean HTML and custom CSS. It is structured to guide visitors through the company's offerings, statistics, services, client reviews, team members, and a contact mechanism, adhering to a cohesive and contemporary design aesthetic.

##  Key Features and Sections

The landing page is organized into distinct, content-rich sections to provide a complete overview of the Nasscorp agency:

| Section | Description | Key Content | 
 | ----- | ----- | ----- | 
| **Header (Hero)** | Primary call-to-action area with a bold headline and background image. | Catchy headline, descriptive paragraph, and primary action buttons (`Get Quote Now`, `Learn More`). | 
| **Stats** | Showcase of core achievements to build trust and credibility. | **Happy Customers (1.5K)**, **Cases Done (3K)**, **Award Winning (45)**, **Countries Worldwide (12+)**. | 
| **Features** | Highlighted list of key business services offered. | Cards for Business Growing, Digital Marketing, National Top 50 Firms, etc. | 
| **Business Service** | Detailed explanation of the company's unique value proposition. | A dedicated section with an image, text, and bulleted trust points. | 
| **Testimonials** | Client reviews presented in a clean, card-based layout to showcase social proof. | Name, designation, star ratings, and review text. | 
| **Team** | Introduction to the core team members. | Team member photos, roles (`CO Founder`, `Consultant`), and names. | 
| **Contact Form** | Dedicated section for lead capture, including name, email, department, and time selection. | Interactive form with an appointment booking button. | 
| **Footer** | Contact information, navigation links, and social media icons. | Company Info, Features, Resources, and Copyright. | 

##  Technology Stack

* **HTML5:** Semantic markup structure.

* **CSS3:** Custom styling for a modern, responsive design.

* **Font:** **Montserrat** is imported and used for all typography, ensuring a clean and professional look.

##  Design & Aesthetics

The design follows a professional, corporate color scheme defined by CSS variables:

* **Primary Accent (`--primary-color`):** `#ffa62b` (Orange/Amber)

* **Secondary Accents:** `#00a0c1` and `#16697a` (Teals/Blues)

* **Text Colors:** Dark text (`#252b42`) and muted secondary text (`#737373`).

* **Layout:** Utilizes Flexbox extensively for responsive grid layouts across various sections.


## Problem & Challanges & Solution:

###  Problem 1: Relative Positioning (CSS)

The unwanted space (approximately 250px) was created because two sections, `#contact-form` and `footer`, used **`position: relative`** combined with a **negative `top` value**.

| Element | Original CSS (Cause) | Effect on Layout |
| :--- | :--- | :--- |
| **`#contact-form`** | `position: relative; top: -350px;` | Visually moves the element up, but **preserves its original 350px of space** in the document flow, pushing the `footer` down. |
| **`footer`** | `position: relative; top: -250px;` | Visually moves the footer up, but **preserves its original 250px of space** at the very end of the document, resulting in the final empty gap. |

**Key Takeaway:** `position: relative` should be avoided for layout adjustments when you need subsequent elements to occupy the vacated space.

---

###  Solution 1: Switching to Negative Margins

The fix involves replacing the `position: relative` and `top` properties with **negative `margin-top`**. Negative margins pull the element up without preserving its original space, allowing the following content to flow correctly.

#### 1. Fix the Contact Form (`./css/style.css`)

I eliminate the footprint of the contact form by removing the positioning and applying a negative margin:

```css
/* ================= Contact Form Start Here================= */

#contact-form {
  /* REMOVED: position: relative; */
  /* REMOVED: top: -350px; */

  /* NEW: Pulls the form up, eliminating its footprint */
  margin-top: -350px; 
}