# Ruby on Rails Recruitment Task EN

## Description and resources

* TL;DR: Develop product and categories system like eBay's
* [Example visualization is here](additional_informations.pdf) - you can see it also in this repository as pdf or xml file (open using [draw.io](https://www.draw.io/))

## Business Requirements

- In application we have given a Category system (Category)
- And the product which is belonging to it (Product)
- Categories have a tree structure, with one root category (Root)
- Product can only belong to one category, the deepest one (for example Root -> Cars -> Opel - so just only to Opel)
- Product has name (string)
- Every category can have unlimited additional attributes in their definition, for example:
	- For Opel:
		- Year (integer)
		- Mileage (integer)
		- Price (decimal)
		- Petrol/Diesel (fuel, dictionary, size of dictionary can be unlimited)
	- But we also can have another category:
		- Root -> Mobile Phones -> Apple -> iPhone
			- Price (decimal)
			- Version (integer)
			- System (string)
	- Categories can inherit attributes dictionary from another category (for example Root -> Cars -> Mercedes inherits attributes from Opel - [see the attachment](additional_informations.pdf)) from the same level category in tree
- Category can have attributes common with other categories (for example price, like in above example) and attributes unique for that category (for example version / mileage above)
- Do not develop user / login system - it's not needed here
- We also need a CRUD in backend where we can create/read/update/delete categories, dynamic attributes, inheritance from another category
- In app we need to also have CRUD where we can manage products, define correctly their dynamic attributes depending on which place in category tree they are laying
- We should have a category listing in application where you are able to navigate through category tree and browse / filter products
	- If you go to parent category, you should see products from child category
	- If you go to child category, i cannot see products from sibling category (so if i'm in Root -> Cars -> Opel i can see only Opel's car, but when i'm in Cars category i can see all Opel/Mercedes/Tesla cars / and when i'm in Root i cann see all possible products in listing)
- When i'm browsing categories, a filter possibilities are changing - so if i'm in root category, i can filter products by price (because all categories and products have such filtering) but when i'm in Opel category we can filter cars using price + mileage + year + petrol / diesel - [see the attachment](additional_informations.pdf))

## Technical Requirements

- Solution needs to be delivered as complete git repository possible to clone (just send us the GitHub repository link)
- You can use any frontend (bootstrap / jquery / vue.js / react) -

## FAQ / Protips

- **Protip: This recruitment task is easy to solve if you will solve it on the paper first - designing database schema which covers all use cases**
- How long that task may take? *Most of people solves it within 2/3 days*
- I need / i can use gems? *The solution is not provided so yo can*
