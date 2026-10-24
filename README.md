Sourcely
Your procurement memory. Find the product. Remember the supplier. Compare the prices.
1. Overview
Sourcely is an Android-first procurement assistant designed to make product sourcing easier for retailers, traders, and purchasing professionals.
In busy wholesale markets, products are sold by numerous suppliers and importers at different prices. Keeping track of every product, quotation, supplier contact, and shop location in your head is difficult, especially for products you do not regularly stock.
You might encounter a product during a market survey, receive a quotation from an importer, or discover a supplier selling a product you rarely need. Weeks later, a customer may request that exact product, but you can no longer remember its price or where you found it.
Sourcely solves this problem by turning market surveys into a searchable procurement database.
Record information when you encounter it. Retrieve it when you need it. Compare your options before making a purchasing decision.
2. The Problem
Retailers and traders often face these challenges:

Forgetting prices quoted by suppliers and importers.
Forgetting where a particular product was seen.
Spending time revisiting markets to find previously discovered products.
Struggling to compare prices across multiple suppliers.
Losing potential sales because a requested product is not stocked and its source cannot be recalled quickly.
Making purchasing decisions using outdated or incomplete information.
Relying on memory to manage large numbers of products and suppliers.

Sourcely provides a practical system for preserving and retrieving this information.
3. Vision
To become a reliable procurement memory that helps businesses find products, remember suppliers, compare sourcing options, and make better purchasing decisions.
Sourcely begins with the information its users collect themselves. Future versions may expand into collaborative procurement intelligence and online supplier discovery.
4. Core Features
4.1 Quick Price Capture
Record a supplier quotation while conducting a market survey or speaking with a supplier.
A price record may include:

Product name and variant.
Brand, size, and packaging.
Quoted price.
Unit of measurement.
Supplier or importer.
Supplier phone number.
Market and shop address.
Section, block, shop number, or nearby landmark.
Date and time of quotation.
Minimum order quantity.
Available quantity, if known.
Delivery or transport costs, if known.
Notes and optional product photographs.

The entry process should be fast, practical, and suitable for use in a busy wholesale market.
4.2 Product Memory
Store products even when they are not part of the user's regular inventory.
A user should be able to record a product encountered during a survey without purchasing it or adding it to their shop stock.
Examples include:

Nivea Lotion
Missa Sunscreen
Products from unfamiliar brands
Special-order items
Products requested by customers but not regularly stocked

4.3 Supplier Directory
Maintain reusable supplier records containing:

Supplier or business name.
Phone numbers and other contact details.
Market and shop address.
Location notes and landmarks.
Supplier category, such as importer, wholesaler, or distributor.
General notes about reliability and purchasing experience.

A supplier can offer many products, and a product can be available from many suppliers.
4.4 Product Search
Search using a product name, brand, size, or relevant keyword.
Search results should retrieve matching products and their recorded supplier quotations.
The system should support practical variations in product names while distinguishing products with different sizes, variants, formulations, or packaging.
4.5 Supplier Price Comparison
When a user searches for a product and enters a required quantity, Sourcely compares the available recorded quotations.
For example:
Product: Nivea Lotion
Required quantity: 10 cartons
The app displays matching suppliers in a useful sourcing order, showing:

Price per comparable unit.
Estimated total product cost.
Known delivery or transport costs.
Minimum order quantity.
Last quoted date.
Supplier contact information.
Supplier address and market location.
Availability or price-confirmation status.

The system should distinguish the lowest quoted price from the best overall purchasing option.
4.6 Quotation History
Every new quotation should be saved as a separate historical record.
Updating a supplier's price must not erase previous quotations.
Users should be able to review historical prices and understand how prices change over time.
4.7 Price Freshness
Sourcely must distinguish between:

A previously recorded quotation.
A recently reconfirmed quotation.
A supplier-confirmed current price.
An unverified or expired quotation.

Historical prices are useful reference information, but they must not be presented as guaranteed current prices.
5. Supplier Ranking Principles
Supplier recommendations should consider multiple factors rather than sorting prices alone.
The initial ranking criteria are:

Product match: The exact product, variant, size, and packaging.
Total cost: Product cost plus known delivery or transport expenses.
Quantity suitability: Whether the supplier can fulfil the required quantity and any minimum-order conditions.
Price freshness: How recently the quotation was recorded or confirmed.
Availability confidence: Whether stock has been confirmed or availability remains unknown.
Location convenience: How practical it is to reach the supplier.
Supplier reliability: Relevant historical experience, where sufficient data exists.

The app should show why a supplier is recommended and allow users to inspect alternative suppliers.
Unknown costs, availability, and other missing information must be clearly identified rather than assumed.
6. Target Users
Sourcely is initially intended for:

Retailers and shop owners.
Wholesale traders.
Procurement officers.
Independent purchasing agents.
Businesses that regularly survey prices across multiple suppliers.
Traders operating in markets such as Balogun Trade Fair and other wholesale markets.

The initial focus is individual use, with the option to support authorised staff and multiple devices in future versions.
7. Initial Scope
The first version should concentrate on four essential workflows:

Record a product and supplier quotation quickly.
Find a previously recorded product.
Compare supplier quotations for a requested quantity.
Retrieve supplier contact details and exact market location.

The initial version will not require online supplier discovery, automated web price collection, public supplier listings, or complex enterprise procurement workflows.
These features may be considered after the core workflow proves useful.
8. Technical Direction
The proposed technology stack is:

Mobile application: Flutter and Dart.
Local storage: A structured local database for fast access and offline data capture.
Backend: Python API, introduced when centralised storage, synchronisation, or multi-user access is required.
Database: SQLite for local storage; a server-side relational database such as PostgreSQL may be introduced for shared deployments.
Version control: Git.

The architecture should separate product information, supplier information, and quotation history.
A future backend must remain responsible for shared data validation, permissions, and synchronisation rules.
The first version should avoid unnecessary infrastructure until the core procurement workflow is validated.
9. Core Data Model
Product
Represents a distinct product or product variant.
Suggested fields:

id
name
brand
variant
size
unit
packaging_description
barcode, optional
notes

Supplier
Represents a supplier, importer, wholesaler, or distributor.
Suggested fields:

id
name
supplier_type
phone
alternate_phone
market
address
section
block
shop_number
landmark
notes

Quotation
Represents a specific price observation from a supplier at a particular time.
Suggested fields:

id
product_id
supplier_id
quoted_price
price_unit
packaging_description
minimum_order_quantity
quoted_at
price_confirmed_at, optional
availability_status
available_quantity, optional
delivery_cost, optional
notes

Historical quotations should be retained rather than overwritten.
Future Extensions
Additional entities may include:

Supplier price confirmations.
Purchase requests.
Procurement comparisons.
Product photographs.
Saved sourcing lists.
User accounts and permissions.
Synchronisation records.

10. Offline-First Design
Market surveys must not depend on a reliable internet connection.
The app should allow users to capture and retrieve locally stored products, suppliers, and quotations without internet access.
If synchronisation is added later, the design should account for duplicate records, conflicting edits, failed uploads, and interrupted connections.
Users must receive clear feedback about whether their data has been saved locally and whether it has synchronised successfully.
11. User Experience Principles
Sourcely should be:

Fast enough for use during active market surveys.
Simple enough to operate with one hand.
Search-first, with minimal navigation.
Clear about historical versus confirmed prices.
Reliable when offline.
Focused on useful procurement decisions rather than unnecessary features.
Designed around practical market locations, including shop numbers and landmarks.

12. Development Roadmap
Phase 1 — Foundation

Set up the Flutter project.
Establish the product, supplier, and quotation data models.
Implement local persistence.
Create the basic navigation structure.

Phase 2 — Capture

Build quick product and quotation entry.
Create and reuse supplier records.
Save market locations and notes.
Add quotation history.

Phase 3 — Search and Compare

Implement product search.
Match product variants accurately.
Accept a required procurement quantity.
Calculate comparable costs.
Rank suppliers and explain the ranking.
Display quotation freshness and supplier locations.

Phase 4 — Practical Improvements

Add filters and sorting.
Add product photographs.
Improve offline usability.
Add contact shortcuts.
Add export and backup capabilities.

Phase 5 — Expansion

Introduce user accounts and shared access.
Add secure cloud synchronisation.
Support team-collected quotations.
Consider purchase requests and supplier performance tracking.
Explore online price discovery as a separate sourcing channel.

13. Success Criteria
The first version is successful if a user can:

Record a supplier quotation in a few simple steps.
Find a product that was surveyed weeks earlier.
Retrieve the correct supplier's contact details and location.
Compare multiple quotations for a specified quantity.
Identify the lowest recorded cost and the most suitable sourcing option.
See when a price was last recorded or confirmed.
Continue capturing and searching records without internet access.

14. Product Philosophy
Sourcely is not initially intended to be another online marketplace.
Its primary purpose is to preserve the procurement knowledge users already acquire in the real world.
Every survey becomes searchable knowledge. Every supplier encounter becomes a useful record. Every saved quotation makes the next sourcing decision easier.
Sourcely — Never lose a supplier, a price, or a sourcing opportunity to memory again.
