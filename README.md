# FetchRecipes
Fetch Mobile Take Home Project

## Summary: Include screen shots or a video of your app highlighting its features

### RecipeListView
This screen displays a list of recipes fetched from the provided endpoint. Each list item (cell) includes a thumbnail image, the recipe’s name, and its associated cuisine. The view gracefully handles edge cases:

- If the endpoint returns malformed `JSON`, an alert is presented to the user with the message: "Server Error. The data received from the server was invalid. Please contact support."
- If the response contains no data, the app presents a friendly empty state with the message: "No recipe found – yet! Looks like there is nothing to show right now. Check back later."
  
![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 16 12](https://github.com/user-attachments/assets/4e5d20d8-a8bc-4264-9964-e68e731a4114)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 41 00](https://github.com/user-attachments/assets/48fff210-510c-448b-88f9-41a418097128)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 42 34](https://github.com/user-attachments/assets/63b35088-8ce6-4323-89bc-0d74d4290ca0)

### RecipeDetailView
When a user taps on a recipe from the list, a `RecipeDetailView` is presented with additional information. This view includes:

- A large image of the recipe loaded from the `photo_url_large`.
- The recipe’s name and its cuisine type displayed prominently.
- A Video button that, when tapped, opens a `SafariView` to display the YouTube video link.
- A Web button that opens a `SafariView` showing the `source_url` for the full recipe webpage.
- A Star button that toggles the recipe as a favorite. When favorited, the star fills in with the Fetch orange color (further details in the favorites section below).
- A dismiss button ("X") in the top left corner allows the user to close the detail view and return to the recipe list.

#### Intelligent Button Handling:

- If the `youtube_url` or `source_url` is `nil`, their respective buttons are hidden entirely preventing user confusion from tapping on a non-functional button.
- As a fallback, if a provided URL fails to load or returns an error, users are automatically redirected to the Fetch homepage, ensuring they always land on a working page rather than a broken experience.

#### Additional UI details:

The background (`RecipeListView`) is softly blurred when the detail view is active, providing a layered, modal like experience via `ZStack`.
A subtle orange halo (Fetch theme color) outlines the detail view for an enhanced visual appeal.

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 16 51](https://github.com/user-attachments/assets/0469c645-2bb9-4857-9770-515a953a76ba)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 16 59](https://github.com/user-attachments/assets/9b5c67b6-cd75-4f0f-a285-ea4cc5f75ab1)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 17 15](https://github.com/user-attachments/assets/dac9949a-92d0-4578-9630-5ce4726c31e9)

### FavoritesListView
The `FavoritesListView` provides quick access to recipes users have marked as favorites. Features include:

- When a user taps the star button in the `RecipeDetailView`, the star fills with the Fetch orange color and the recipe is saved to the `FavoritesListView`.
- Tapping the star again removes the recipe from favorites the star becomes unfilled, and the recipe is removed from the `FavoritesListView`.
- Users can also swipe left on a recipe cell in the `FavoritesListView` to reveal a Delete action. Tapping delete removes the recipe from the list and updates the corresponding star in the `RecipeDetailView` to its unfilled state.
- Tapping a recipe in the `FavoritesListView` opens its `RecipeDetailView`, with the `FavoritesListView` blurred in the background using a `ZStack`.
- A halo effect in the Fetch purple color outlines the screen when viewing a recipe from the `FavoritesListView`, adding visual distinction and polish.

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 17 24](https://github.com/user-attachments/assets/87c76289-b605-4ec9-a616-ec9fd25efeef)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 17 31](https://github.com/user-attachments/assets/9287c4d3-5396-43cd-b605-3256358c98f2)

![Simulator Screenshot - iPhone 16 Pro - 2025-06-19 at 15 17 40](https://github.com/user-attachments/assets/8b9d6bbb-cb53-4acc-9ca6-b89f0dcd0714)


## Focus Areas: What specific areas of the project did you prioritize? Why did you choose to focus on these areas?

### I prioritized user experience ensuring the app felt intuitive, reliable, and visually polished. Below are the key areas I focused on to deliver that:

#### Seamless UI/UX Design

- I designed the app to be intuitive and easy to navigate, so users could explore recipes without confusion.
- The visual design uses a color palette inspired by the Fetch brand to create a cohesive, branded experience that feels like a natural extension of Fetch's identity.
- Views like the `RecipeDetailView` use subtle visual touches (e.g. blurred backgrounds, orange halo effects) to enhance clarity and polish while maintaining visual depth via `ZStack`.

#### Enhanced Usability Features

- I added a `FavoritesTab` as an extra feature to make it easier for users to save and quickly return to recipes they love eliminating the need to scroll or search the list again.
- Recipes can be favorited by tapping the star button in the detail view. They appear in the `FavoritesListView`, and can be removed by tapping the star again or swiping to delete.
- This feature was implemented with syncing behavior: removing a recipe from favorites also updates the star icon across views, keeping everything in sync.

#### Clear Error Handling & Feedback

- If the API returns no data, instead of showing a blank screen, the app displays a friendly empty state message:
“No recipe found – yet! Looks like there is nothing to show right now. Check back later.”
- If the data is malformed or unreadable, the app presents a clear error alert:
“Server Error. The data received from the server was invalid. Please contact support.”
- This ensures users aren’t confused about whether the app is broken, still loading, or simply missing content everything is communicated clearly and non-technically.

#### Loading States & Responsiveness

- To ensure the app feels responsive, I prioritized caching images and showing loading indicators wherever content is being fetched.
- Whether it's recipe images or full screen views, users are given clear visual cues that content is loading avoiding the perception that the app is frozen or slow.

#### Intelligent Link Handling

- If a recipe is missing a `youtube_url` or `source_url`, the respective buttons are hidden. This prevents users from tapping a button that won’t work, removing any guesswork.
- As a fallback, if a provided URL fails to load or encounters an error, the app redirects users to the Fetch homepage to ensure they always land on a live, functional page.

## Time Spent: Approximately how long did you spend working on this project? How did you allocate your time?

### I spent approximately 10 hours working on this project, thoughtfully allocating my time across planning, development, and refinement. Here's how the time was broken down:

#### 3 hours – Planning & Research
- I began with research and ideation: exploring color palettes that matched Fetch's branding, gathering UI inspiration from similar apps, brainstorming potential feature enhancements, and wireframing the core layout.

#### 2 hours – Initial UI Development
- I built the foundation of the app by laying out the main screens and setting up the views that would be used throughout the app. This phase also included structuring sample data to visualize how real content would appear.

#### 2 hours – Networking & Data Handling
- I integrated the real API data through network calls, making sure information was properly parsed and displayed in the app. This also included adding functionality to save and remove recipes from the `FavoritesListView`, and handling edge cases like empty or invalid responses.

#### 1 hour – Image Caching
- I implemented `CachedAsyncImage` to efficiently handle image loading, improving performance and reducing flickering or delays during repeated navigation.

#### 2 hours – Final UX Enhancements & Bug Fixes
- I wrapped up by testing the app, polishing edge cases, and adding thoughtful user experience improvements such as hiding buttons when links are `nil` and ensuring fallback behaviors were in place for broken or missing URLs.

## Trade-offs and Decisions: Did you make any significant trade-offs in your approach?
- One key trade-off I made was in how I implemented image caching. I opted to use a simple `[URL: Image]` dictionary to cache images rather than implementing a more robust solution with `NSCache`.
- While `NSCache` is the better long-term solution offering built-in memory management, thread safety, and eviction policies I prioritized shipping a functional and user friendly experience over technical perfection in this area. My main focus was ensuring users had a responsive, clean UI rather than optimizing caching under the hood. With more time, switching to `NSCache` would be a natural next step to improve performance and scalability, especially for production use.

## Weakest Part of the Project: What do you think is the weakest part of your project?
The weakest part of the project is definitely the image caching system.
Using a `[URL: Image]` dictionary works for prototyping, but it lacks important production-ready features:

- No memory management or eviction (risking memory leaks).
- Not thread safe (could cause crashes in concurrent access).
- Doesn’t scale well or handle memory pressure on constrained devices.

A better alternative would have been `NSCache<NSURL, UIImage>`, which provides:

- Automatic eviction under low memory conditions.
- Thread safety out of the box.
- Built-in cache limits.
- Better testability with `UIImage`.
  
I went with the dictionary approach mainly because I realized image caching was needed mid-way through the project, and my schedule was tight. Had I invested more time, I would’ve implemented `NSCache` for a more scalable and reliable solution.

## Additional Information: Is there anything else we should know? Feel free to share any insights or constraints you encountered.
I completed this project gradually over several days, often working in one hour sessions due to other ongoing commitments. There were occasional breaks between work sessions, but overall I found the project to be an enjoyable and valuable opportunity to explore my skills particularly in building clean UI, handling network data, and thinking through user experience holistically.

Despite the time constraints, I focused on delivering a thoughtful and functional experience that reflects both my attention to detail and my ability to make product focused decisions under real world conditions.
