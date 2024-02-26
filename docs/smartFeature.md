
## UI Layer
The [UI layer](https://developer.android.com/topic/architecture/ui-layer) comprises:


*   UI elements built using XML.
*   [Android ViewModels](https://developer.android.com/topic/libraries/architecture/viewmodel)

The ViewModels receive streams of data from use cases and repositories and transform them into UI state. The UI elements reflect this state, and provide ways for the user to interact with the app. These interactions are passed as events to the ViewModel where they are processed.

![architecture-1-ui-layer](https://github.com/osamasayed585/Lnj/assets/68209547/359af80d-6c49-47fc-9513-7389bd919b14)

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

