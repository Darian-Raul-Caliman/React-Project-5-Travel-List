
<img width="1133" height="587" alt="Captură de ecran 2025-07-13 191516" src="https://github.com/user-attachments/assets/9bfdcfb7-65e4-4fab-ab78-bc613decbb20" />


This is a simple React application that helps users manage a packing list for trips. You can add items, mark them as packed, sort the list, and delete individual or all items. The app demonstrates fundamental React concepts such as components, state management, props, forms, conditional rendering, and list rendering.

Components Overview
✅ App.js — Main App Component
This is the root component of the application. It holds the global state and orchestrates communication between child components.

Key Features:
Maintains the items state using useState.

Functions:
handleAddItems(item): Adds a new item to the list.
handleDeleteItem(id): Removes an item by its id.
handleToggleItem(id): Toggles the packed status of an item.
handleDelete(): Deletes all items after a confirmation prompt.

Renders:
<Logo />: App logo/title.
<Form />: For adding new items.
<PackingList />: Displays the item list and sorting controls.
<Stats />: Shows summary statistics.

✍️ Form.js — Add New Items
This component handles user input for adding new items.

Key Features:
Internal state:
description: String input for item name.
quantity: Number input (1–20) for quantity.
On form submit:
Prevents page reload.
Creates a new item object:

js
Copy
Edit
{ description, quantity, packed: false, id: Date.now() }
Passes it to onAddItems() (from App).
Resets the input fields.

📦 PackingList.js — List and Sort Items
Displays the packing list with sorting and clearing functionality.

Props:
items: List of items to render.
onDeleteItem: Function to delete an individual item.
onToggleItems: Function to toggle an item's packed status.
onDeleteAll: Function to clear all items.

Internal State:
sortBy: Controls the sorting logic (input, description, packed).

Features:
Sorts the list based on the selected sortBy value:
input: Original order
description: Alphabetical by description
packed: Unpacked items first
Renders each item using <Item />.
Dropdown to change sorting.
Button to clear the list.

✅ Stats.js — List Summary
Displays dynamic feedback at the bottom of the app.

Features:
Shows a message if no items exist.

Calculates:
numItems: Total number of items.
numPacked: Items marked as packed.
percentage: Percent packed.

Displays a message like:
"You got everything packed! 🎉" when 100% packed.
Or: "You have 6 items on your list, and you already packed 50%!!"
