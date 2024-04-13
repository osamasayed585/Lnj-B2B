
## UI Layer
The [UI layer](https://developer.android.com/topic/architecture/ui-layer) comprises:


*   UI elements built using XML.
*   [Android ViewModels](https://developer.android.com/topic/libraries/architecture/viewmodel)

The ViewModels receive streams of data from use cases and repositories and transform them into UI state. The UI elements reflect this state, and provide ways for the user to interact with the app. These interactions are passed as events to the ViewModel where they are processed.

![xmlpng](https://github.com/osamasayed585/Lnj-B2B/assets/68209547/762c8804-a82f-45e8-ae36-b7a3a5ad1f18)



# TempCartFragment

The `TempCartFragment` manages temporary shopping cart functionality in the Android app.

## Main Component

- **ViewModels:**
  - `sharedViewModel`: Shared view model for inter-fragment communication.
  - `viewModel`: Manages UI data and interactions for the temporary cart.

- **Adapters:**
  - `verticalDealsAdapter`: Displays vertical deals.
  - `horizontalDealsAdapter`: Displays horizontal deals.
  - `productsAdapter`: Displays temporary products.
  - `comparingTableAdapter`: Displays comparing tables.
  - `comparingDealPriceAdapter`: Displays comparing deal prices.

- **Data Collections:**
  - `availableProducts` and `unavailableProducts`: Lists for products in the temporary cart.
  - `industries`: List of sectors.
  - `deals`: List of deals for the selected sector.
  - `products`: List of temporary products.

## Usage

1. **ViewModel Initialization:**
   - Initialize `sharedViewModel` and `viewModel` for communication and UI management.

2. **Adapter Usage:**
   - Utilize adapters for displaying deals, products, and comparing tables.

3. **Data Handling:**
   - Manage available and unavailable products, sectors, deals, and temporary product lists.

4. **Lifecycle Methods:**
   - `onCreate`: Initializes the fragment and requests industries.
   - `onViewCreated`: Sets up UI components, observes LiveData, and handles clicks.

5. **UI Display Modes:**
   - Toggle between display modes: `HORIZONTAL`, `VERTICAL`, and `COMPARING_TABLE`.

6. **User Interactions:**
   - Delete/update products, review orders, and confirm items.

7. **Navigation:**
   - Navigate to different app destinations (e.g., completion of shopping or order review).

8. **Resource Handling:**
   - Display deals, products, and comparing tables based on data availability.


# TempCartViewModel

The `TempCartViewModel` is responsible for managing data and business logic related to the temporary shopping cart in the Android app.

## Main Component

- **StateFlows:**
  - `industries`: Provides information about available sectors.
  - `sectorDetail`: Represents details of a selected sector.
  - `addDealToCart`: Emits the status of adding a deal to the cart.
  - `deleteProduct`: Emits the status of deleting a product from the cart.
  - `updateProduct`: Emits the status of updating a product in the cart.
  - `currentDisplayMode`: Represents the current display mode (e.g., HORIZONTAL, VERTICAL).

## Usage

1. **Initialization:**
   - Instantiate the `TempCartViewModel` using Dagger-Hilt injection.

2. **LiveData Observing:**
   - Observe LiveData to receive updates on industries, sector details, and cart operations.

3. **Display Mode Handling:**
   - Use `setDisplayMode` to set the display mode for deals and products.

4. **Adding a Deal to Cart:**
   - Call `requestAddDealToCart` to add a deal to the temporary cart.

5. **Refreshing Cart:**
   - Use `refreshTempCart` to update the temporary cart details for a specific sector.

6. **Deleting/Updating Products:**
   - Call `requestDeleteProduct` and `requestUpdateProduct` to handle product operations.

7. **Requesting Sector Details and Confirmation:**
   - Use `requestSectorDetail` and `requestSectorConfirmation` to fetch sector details and confirmations.

8. **Requesting Industries:**
   - Call `requestIndustries` to retrieve a list of available industries.

## Miscellaneous

- **Error Handling:**
  - The ViewModel handles loading states and error responses gracefully.

- **Coroutines:**
  - Utilizes coroutines for asynchronous operations.

- **Dependencies:**
  - Utilizes various use cases for industry retrieval, cart operations, and sector details.

