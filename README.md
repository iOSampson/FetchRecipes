# FetchRecipes
Fetch Mobile Take Home Project

### Summary: Include screen shots or a video of your app highlighting its features

#### RecipeListView
This screen displays a list of recipes fetched from the provided endpoint. Each list item (cell) includes a thumbnail image, the recipe’s name, and its associated cuisine. The view gracefully handles edge cases:

- If the endpoint returns malformed JSON, an alert is presented to the user with the message: "Server Error. The data received from the server was invalid. Please contact support."
- If the response contains no data, the app presents a friendly empty state with the message: "No recipe found – yet! Looks like there is nothing to show right now. Check back later."
  
![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 16 12](https://github.com/user-attachments/assets/4e5d20d8-a8bc-4264-9964-e68e731a4114)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 41 00](https://github.com/user-attachments/assets/48fff210-510c-448b-88f9-41a418097128)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 42 34](https://github.com/user-attachments/assets/63b35088-8ce6-4323-89bc-0d74d4290ca0)

#### RecipeDetailView
When a user taps on a recipe from the list, a RecipeDetailView is presented with additional information. This view includes:

- A large image of the recipe loaded from the photo_url_large.
- The recipe’s name and its cuisine type displayed prominently.
- A Video button that, when tapped, opens a SafariView to display the YouTube video link.
- A Web button that opens a SafariView showing the source URL for the full recipe webpage.
- A Star button that toggles the recipe as a favorite. When favorited, the star fills in with the Fetch orange color (further details in the favorites section below).
- A dismiss button ("X") in the top-left corner allows the user to close the detail view and return to the recipe list.

Additional UI details:

The background (RecipeListView) is softly blurred when the detail view is active, providing a layered, modal-like experience via ZStack.
A subtle orange halo (Fetch theme color) outlines the detail view for an enhanced visual appeal.

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 16 51](https://github.com/user-attachments/assets/0469c645-2bb9-4857-9770-515a953a76ba)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 16 59](https://github.com/user-attachments/assets/9b5c67b6-cd75-4f0f-a285-ea4cc5f75ab1)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 17 15](https://github.com/user-attachments/assets/dac9949a-92d0-4578-9630-5ce4726c31e9)

#### FavoritesView
The FavoritesView provides quick access to recipes users have marked as favorites. Features include:

- When a user taps the star button in the RecipeDetailView, the star fills with the Fetch orange color and the recipe is saved to the FavoritesView.
- Tapping the star again removes the recipe from favorites—the star becomes unfilled, and the recipe is removed from the FavoritesView.
- Users can also swipe left on a recipe cell in the FavoritesView to reveal a Delete action. Tapping delete removes the recipe from the list and updates the corresponding star in the RecipeDetailView to its unfilled state.
- Tapping a recipe in the FavoritesView opens its RecipeDetailView, with the FavoritesView blurred in the background using a ZStack.
- A halo effect in the Fetch purple color outlines the screen when viewing a recipe from the FavoritesView, adding visual distinction and polish.

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 17 24](https://github.com/user-attachments/assets/87c76289-b605-4ec9-a616-ec9fd25efeef)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 17 31](https://github.com/user-attachments/assets/9287c4d3-5396-43cd-b605-3256358c98f2)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 17 40](https://github.com/user-attachments/assets/8b9d6bbb-cb53-4acc-9ca6-b89f0dcd0714)


### Focus Areas: What specific areas of the project did you prioritize? Why did you choose to focus on these areas?

### Time Spent: Approximately how long did you spend working on this project? How did you allocate your time?

### Trade-offs and Decisions: Did you make any significant trade-offs in your approach?

### Weakest Part of the Project: What do you think is the weakest part of your project?

### Additional Information: Is there anything else we should know? Feel free to share any insights or constraints you encountered.
