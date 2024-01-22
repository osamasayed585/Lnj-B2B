![Lnj B2B app](docs/images/lnj_b2b_spalsh.png "lnj b2b spalsh")

<a href="https://play.google.com/store/apps/details?id=com.sa.lnj"><img src="https://play.google.com/intl/en_us/badges/static/images/badges/en_badge_web_generic.png" height="70"></a>



Lnj Merchants App
==================

**Lnj Merchants App Repository is an ongoing project,🚧 Look how this app was designed and built in the [design case study](https://goo.gle/nia-figma](https://www.figma.com/file/IN2kItj0Uecjwguriit22U/LNJ---Merchant-App?type=design&mode=design&t=5RMadKxPufCaTTfp-1)), and [architecture learning journey](docs/ArchitectureLearningJourney.md).**

# Features

**Lnj Merchants App** is a revolutionary B2B e-commerce platform connecting wholesalers and distributors with retailers. It simplifies the buying and selling journey, ensuring an effortless, efficient, and cost-effective procurement process.

#### Smart Comparison [Enabled] ✅
- Users can select products without initially viewing prices.
- Confirm selected items in the temp cart, allowing the system to aggregate and present personalized deals.
#### Normal Flow [Disabled] 🚫
- Enables users to choose suppliers and products with predefined prices, adding them to the main cart.
#### Companies Flow [Disabled] 🚫
- Allows users to select a specific company, choose products with specified prices, and add them to the main cart.
#### Side Menu [Enabled] ✅
- The Lnj Merchants App provides a user-friendly side menu, offering easy access to essential features such as order history, offers, wallet, notifications, settings, and contact options. Navigate seamlessly through these functionalities to enhance your overall B2B e-commerce experience. Focus on smart purchasing decisions and efficient transactions with the Lnj Merchants App.

## Screenshots

![Screenshot showing Home screen, Smart screen, Cart screen and Product screen](docs/images/screenshot.jpg "Screenshot showing Home screen, Smart screen, Cart screen and Product screen")

# Development Environment

**Lnj Merchants App** uses the Gradle build system and can be imported directly into Android Studio, ensure you are using 
- Android Studio Hedgehog | 2023.1.1 Patch 1 [here](https://developer.android.com/studio/archive) 
- Kotlin Version: 1.9.22
- Android Gradle Plugin Version: 8.2

Change the run configuration to `app`.

![image](docs/images/configuration_to_app.PNG)

Once you're up and running, you can refer to the learning journeys below to get a better
understanding of which libraries and tools are being used, the reasoning behind the approaches to
UI, architecture, and more, and how all of these different pieces of the project fit
together to create a complete app.

# Architecture

The **Lnj Merchants** app follows the
[official architecture guidance](https://developer.android.com/topic/architecture) 
and is described in detail in the
[architecture learning journey](docs/ArchitectureLearningJourney.md).


# UI
The app was designed using [Material 2 guidelines](https://m2.material.io/). Learn more about the design process and 
obtain the design files in the [Lnj Merchants App Material 2 Case Study](https://www.figma.com/file/IN2kItj0Uecjwguriit22U/LNJ---Merchant-App?type=design&mode=design&t=5RMadKxPufCaTTfp-1)).
The Screens and UI elements are built entirely using [Layouts in Views](https://developer.android.com/develop/ui/views/layout/declaring-layout). 

The app has a single-light mode theme

Find out more about the [UI architecture here](docs/ArchitectureLearningJourney.md#ui-layer).

## Built With 🛠

- [Kotlin](https://kotlinlang.org/) - First class and official programming language for Android
  development.
- [Coroutines](https://kotlinlang.org/docs/reference/coroutines-overview.html) - For asynchronous
  and more..
- [Android Architecture Components](https://developer.android.com/topic/libraries/architecture) -
  Collection of libraries that help you design robust, testable, and maintainable apps.
    - [Flows](https://developer.android.com/kotlin/flow) - A flow is a type that can emit multiple
      values sequentially, as opposed to suspending functions that return only a single value.
    - [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel) - Stores
      UI-related data that isn't destroyed on UI changes.
    - [Jetpack Navigation](https://developer.android.com/guide/navigation) - Navigation refers to
      the interactions that allow users to navigate across, into, and back out from the different
      pieces of content within your app
    - [Hilt](https://developer.android.com/training/dependency-injection/hilt-android) - Hilt is a
      dependency injection library for Android that reduces the boilerplate of doing manual
      dependency injection in your project.
        - [Retrofit](https://square.github.io/retrofit/) - Is a type-safe REST client for Android
          which
          aims to make it easier to consume RESTFUL web services.
    - [Glide](https://bumptech.github.io/glide/) - An image loading and caching library for Android.
      <br />

## Architecture 🗼

This app uses [***Clean Architecture***](https://developer.android.com/topic/architecture) With [
***MVVM (Model View
View-Model)***](https://developer.android.com/jetpack/docs/guide#recommended-app-arch) architecture.

![](docs/images/AndroidTemplate-CleanArchitecture.png)

![](docs/images/mvvm.webp)
