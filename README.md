# Business Process Integration: Supply Chain Management System

This repository contains the final report and presentation for a project developed for the **Business Process Integration Lab** course at the University of Twente. The project involved modeling, designing, and implementing a software solution to manage the logistics of a Transport Company within a simulated supply chain.

## Table of Contents
1.  [Project Overview](#project-overview)
2.  [The Challenge](#the-challenge)
3.  [Our Solution](#our-solution)
4.  [Key Technologies](#key-technologies)
5.  [Unique Feature: Competitive Advantage](#unique-feature-competitive-advantage)
6.  [Challenges & Reflections](#challenges--reflections)
7.  [Team Members](#team-members)
8.  [Project Deliverables](#project-deliverables)

## Project Overview

Our team assumed the role of a **Transport Company (TC)** operating within the supply chain of "Uniprocterlevergamble Ltd.", a large producer of Fast Moving Consumer Goods. The objective was to build a system that could manage transport orders, optimize logistics by collaborating with other TCs, and communicate with central Control Towers (CTs) to ensure the timely and cost-effective delivery of goods.

## The Challenge

The primary technical challenge was to create an efficient inter-organizational system for handling **Less-Than-Truckload (LTL)** shipments. When a shipment did not fill a full truck, our system needed to communicate with other TCs to find partners to combine loads, thereby reducing costs and increasing efficiency for all parties. This required designing and adhering to standardized data protocols for seamless interoperability between systems developed by different teams.

## Our Solution

We developed a fully functional application using the Mendix low-code platform. The application served as our company's operational dashboard and the gateway to interacting with the broader supply chain network.

### Mendix Application
The application features a user interface for managing internal orders, assigning drivers, and tracking deliveries. Its core functionality is the **"Bid Market,"** which connects to the inter-company logistics network.

### Inter-Company Bidding System
To solve the LTL challenge, our group and other TCs co-designed a two-part system:
* **Central Hub**: A shared **Google Firebase** database was used as a central marketplace where all TCs could post their available LTL shipments.
* **Private Bidding**: TCs could place bids on each other's LTL shipments via a series of private **REST API endpoints**. This allowed companies to negotiate and combine shipments to create a Full Truckload (FTL). Our application fully implemented the necessary API calls to post LTLs, bid on others, and accept/deny bids on our own orders.

### Control Tower Communication
The system was designed to communicate finalized transport plans to the Control Towers using a **SOAP API** with an **XML** payload. However, due to significant communication delays and late delivery of the required WSDL schema from the CT teams, this component could not be fully implemented.

## Key Technologies
* **Application Development:** Mendix
* **Process Modeling:** ArchiMate
* **Database:** Google Firebase
* **APIs & Data Formats:** REST, JSON, SOAP, XML

## Unique Feature: Competitive Advantage

A key strategic decision in our design was to enhance data privacy to gain a competitive edge. While other teams posted all order details publicly, our system was built to **only share minimal information** on the public Firebase hub. Full, sensitive order details were only revealed to the winning bidder after a deal was accepted. This approach protected our operational data while allowing us to analyze the fully transparent data from our competitors to make more strategic bids and create competitive prices.

## Challenges & Reflections

This project was a valuable simulation of real-world interoperability challenges. Key takeaways include:
* The rigidity of the waterfall model is ill-suited for multi-stakeholder projects with evolving requirements; an **Agile methodology** would have been more effective.
* **Clear, consistent communication** is paramount. Misalignments and last-minute protocol changes by other teams caused significant setbacks.
* Understanding the **limitations of your tools** early is crucial. We had to create custom Java actions to overcome Mendix's inability to parse the dynamic JSON keys from Firebase, which was an unexpected hurdle.

## Team Members
* **David Galati**
* Emma Cañavate
* Lars Klunder
* Miguel De La Cruz

## Project Deliverables
* **[Final Report](./group%2025%20BPIL%20Final%20report.pdf)**: The complete project report detailing the case, design decisions, and implementation.
* **[Final Presentation](./g_25_BPIL%20presentation.pptx)**: The presentation summarizing the project's key aspects and outcomes.
