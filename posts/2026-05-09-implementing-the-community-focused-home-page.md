---
title: Implementing the Community-focused Homepage
date: 2026-05-09
author: Runyu Zhou
summary: This post reflects on the implementation of the redesigned homepage, including the top navigation, two-path user entry, local image assets, visual refinements, and the need to preserve existing page functionality while improving the community hub experience.
tags:
  - home-page
  - technical-decisions
  - visual-refinement
---

# Implementing the Community-focused Homepage

After finalising the item detail page and the overall visual direction, I began implementing the new homepage in code. The focus of this implementation was not simply to replace the page’s styling, but to ensure the homepage more clearly supported the site’s positioning as a community hub. The new homepage needed to distinguish between two core user pathways: users wishing to purchase individual items could navigate to ‘Browse Listings’, whilst those wishing to buy or sell multiple items at once, view clearance sales due to moving house, or post bulk requests could navigate to the ‘Community Board’.

To avoid affecting the pages already completed by team members, I developed on a new feature branch first. As the homepage involves global navigation, layout, CSS and some reusable partials, making changes directly on the main branch would result in higher restoration costs should the outcome be unsatisfactory or impact other pages.

A key change in this implementation was shifting the navigation structure from a sidebar-based layout to a top navigation bar. Top navigation is better suited to the current web homepage, as it is a long-form page that needs to guide users from the hero section to continue browsing different content areas. It also keeps key entry points—such as Home, Community, Browse, Share an Item, Messages and Profile—clear, whilst avoiding the sidebar taking up horizontal space. The aim here is not to rewrite other pages, but to make the site-wide visual framework more in line with web application conventions.

Regarding the homepage content, I have implemented a dual-path decision module. The ‘Buying one item?’ option on the left directs users to the ‘Browse’ section, as this path is suitable for users who already know what they are looking for. The ‘Buying many items at once?’ option on the right directs users to the ‘Community Board’, as this page is better suited for handling bundle deals, moving-out posts and bulk offers. This module directly addresses the two user scenarios identified during the requirements analysis and wireframe stages.

I also incorporated local image assets to enhance the homepage’s visual impact. Images are centrally stored in `public/images/home/` and named according to their purpose, ensuring clear file paths and simplifying future maintenance. The hero image depicts scenarios involving international students in Sydney, moving house, and the sharing of second-hand resources; meanwhile, the images within the ‘Move-in Essentials’ cards help users quickly understand the different lifestyle categories.

During the implementation process, I also made several minor visual adjustments. For example, as the hero image itself has a light background, I adjusted the banner background colour to allow the image to blend more naturally with the page. Initially, the images in the ‘Move-in Essentials’ section did not fully fill the card area, so I used CSS to adjust the image dimensions and container spacing to make the cards look more complete. The icons in the dual-path module also needed to be enlarged and centred, as the transparent PNGs inherently contain white space, meaning the default size made the circular area appear underutilised.

This project made me realise that coding is not merely about replicating high-fidelity mock-ups, but about striking a balance between design objectives, technical architecture and team collaboration. The homepage needs to better align with its positioning as a community hub, whilst avoiding changes to the functional content of existing pages such as Community, Browse, Messages, My Page, Post Item and Listing Detail. Ultimately, the homepage is not only visually more complete, but also more clearly supports the two core pathways of ‘single-item browsing’ and ‘community-based bulk posting’.
