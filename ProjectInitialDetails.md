# Project Initial Details

**Team 9 Members**: Yong Xin, Chee Hsien, Naufal, Shania, Thoha

**Git Repository**: <https://github.com/ongyx/INF1103-Group9Project1>

## 1.	Problem Statement and Target Users

### What real-world problem does your application aim to solve?

In public spaces with high volumes of traffic such as airports, hospitals, or malls, the management authority would have a lost-and-found office for members of the public to retrieve their items if left behind.

However, manually keeping track of these items would be difficult for workers to handle depending on the volume of incoming items, especially if lost-and-found items are odd-sized and kept in a separate warehouse.

Therefore, our proposed application aims to solve this problem by:
1.	Implementing an AI-powered fuzzy search engine to search for and recommend similar items by description from a lost-and-found item database
2.	Allowing users to filter and sort recommendations to determine if the lost-and-found item is correct and can be returned to its rightful owner
3.	Providing an avenue for users to submit lost items they have found more easily

This alleviates the workload of workers within the lost-and-found office, simplifies auditing of returned items, and frees up manpower previously spent on tracking items to be distributed elsewhere.

### Who are the intended users of the application?

The target users are members of the public and lost-and-found workers.

## 2.	User Inputs

### What information or data will users provide to the system?

The lost-and-found worker will input a detailed description of any lost item into the system:
1.	A description of the item’s physical appearance and relevant attributes.
    - For example, “500ml blue Nalgene water bottle with a braided rope keychain”.
2.	The date and time when the item was found.
3.	The location where the item was found.
4.	The item’s storage location for the worker to retrieve the item afterwards.
5.	The particulars of the person who the item was returned to, if the item was returned.

When a member of the public wishes to retrieve their item, they will specify:
1.	A description of their item’s physical appearance.
2.	Optionally, the date and time when the item was lost.
3.	Optionally, the location where the item was lost.

The lost-and-found worker will then verify that the item belongs to the member of the public and return the item to them. After this, their particulars are recorded in the item’s database entry for follow-up actions or auditing if necessary.

## 3.	Use of AI

### How will AI be utilized within the application?

It will be used as a fuzzy search over the entire database to suggest items of similar description to the one given by the user. The description can contain additional context such as the date, time, and location lost to narrow down the search further.

### What outputs, insights, or recommendations will the AI generate from the user inputs?

The AI model will rank recommended items according to a confidence value from 0 to 1 for the user to find their item more efficiently. Higher values are more likely to correspond to the item being searched for.

Along with the confidence value, the database entry corresponding to the recommended item will be returned to the user for further filtering or sorting by the application.

## 4.	Business Rules

### What business rules, validations, or decision-making logic will be applied to the AI-generated outputs?

1.	The suggested lost-and-found items can be sorted, searched, and filtered by their confidence value, along with the other database fields such as description, time, and location/flight code.
2.	If there are no results from the AI search, the user will be informed that no item with a similar description was found.
3.	If the item is a high value item (e.g., laptop, wallet, phone), the item will be flagged as high value within the database. The lost-and-found worker will then require additional authentication from the member of the public to claim.
4.	Item entries must include a clear and sufficient detailed description that allows the item to be distinguished from other items in the database. Attempts to submit item entries without descriptions will not be accepted.

