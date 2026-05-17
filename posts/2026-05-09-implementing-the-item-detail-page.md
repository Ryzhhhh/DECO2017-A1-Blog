---
title: Implementing the item Detail Page
date: 2026-05-09
author: Runyu Zhou
summary: This post reflects on the implementation of the listing detail page, including route design, MVC separation, service-layer data handling, template decisions, responsive styling, and the trade-offs made to keep the prototype focused and feasible.
tags:
  - implementation
  - item-detail
  - technical-decisions
---

# Implementing the item Detail Page

This time, I primarily completed the implementation of the `item-detail` page in the BlaBla Corp prototype. Based on the provided wireframe, I created a new `/listing/:id` page, allowing users to navigate from the listing card to the individual product detail page. The overall implementation adhered to the project’s existing technical constraints: Node.js, TypeScript, Mojo.js and server-side rendered templates, without introducing React, Vue or complex front-end state management.

Architecturally, I split the functionality in accordance with the MVC pattern. In the routing layer, I added a `GET /listing/:id` route in `src/index.ts`, pointing to the new listing controller. The controller is solely responsible for reading route parameters, calling services, handling 404 errors, and rendering the page. The specific data retrieval logic is placed in `src/services/listingService.ts`, which uses `getListingById(id)` to retrieve the listing information required for the page from the existing product data. This avoids embedding business logic within the controller or template.

Regarding page templates, I have added `views/listing/show.html.tmpl`. This page implements a two-column layout based on the wireframe: the left-hand side features a large image area, thumbnails and action buttons, whilst the right-hand side displays the product title, price, status, seller information, collection/delivery options, address, publication date, payment methods and product description. As the current database does not yet contain complete fields for sellers, locations, payment methods and images, this version uses appropriate fallbacks; for example, the location is displayed as ‘Chippendale’, payment methods are shown as ‘Card/Cash/Alipay’, and the image area uses the product’s first letter as a placeholder.

I have also updated the navigation logic for listing cards. Product cards in ‘My Page’ now link to `/listing/<id>`, rather than remaining on the current page. The ‘Contact the seller’ button on the details page now correctly links to the existing messaging workflow at `/messages/product/<id>`. The ‘Favourite’ and ‘BUY NOW’ buttons currently serve only as UI elements and do not involve database or payment logic, which is in line with the scope of this task.

In terms of styling, I have added responsive layout support to `public/styles.css`. The desktop version retains the wireframe’s left-image-right-information structure, whilst the mobile version automatically switches to a single-column stacked layout. Basic styling has also been applied to buttons, focus states, semantic HTML, image alt text and keyboard accessibility.

Finally, I ran and verified that `npm run build`, `npm run lint` and `npm test` all passed. I also manually checked that `/listing/1` displays correctly, invalid IDs return a 404 error, cards navigate to the details page, and the ‘Contact Seller’ link works correctly. Overall, this update represents a focused and minimal implementation of the product detail page, laying the groundwork for the subsequent integration of real images, favourites, and more comprehensive seller data.

