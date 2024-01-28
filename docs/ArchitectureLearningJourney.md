# Architecture Journey

In this journey, you will look at the Lnj Merchants app architecture: its layers, key classes, and the interactions between them.

## Goals and requirements
The goals for the app architecture are:

*   Follow the [official architecture guidance](https://developer.android.com/jetpack/guide) as closely as possible.
*   Easy for developers to understand, nothing too experimental.
*   Support multiple developers working on the same codebase.
*   Minimize build times.

## Architecture Overview

The app architecture has three layers: a [data layer](https://developer.android.com/jetpack/guide/data-layer), a [domain layer](https://developer.android.com/jetpack/guide/domain-layer), and a [UI layer](https://developer.android.com/jetpack/guide/ui-layer).

<center>
<img src="images/architecture-1-overall.png" width="600px" alt="Diagram showing overall app architecture" />
</center>

The architecture follows a reactive programming model. With the data layer at the bottom, the key concepts are:

*   Higher layers react to changes in lower layers.
*   Events flow down.
*   Data flows up.

The data flow is achieved using streams, implemented using [Kotlin Flows](https://developer.android.com/kotlin/flow).

### Example: Displaying sliders on the Home screen

When the app is first run it will attempt to load a list of images resources from a remote server. Once loaded, these are shown to the user on the home screen.

The following diagram shows the events which occur and how data flows from the relevant objects to achieve this.


![whole architecture](https://github.com/osamasayed585/Lnj-Merchants-App/assets/68209547/117a1cd6-9ac9-454a-95ab-b495fae92694)

Here's what's happening in each step. The easiest way to find the associated code is to load the project into Android Studio and search for the text in the Code column (handy shortcut: tap <kbd>⇧ SHIFT</kbd> twice).

<table>
  <tr>
   <td><strong>Step</strong>
   </td>
   <td><strong>Description</strong>
   </td>
   <td><strong>Code </strong>
   </td>
  </tr>
  <tr>
   <td>1
   </td>
   <td>The <code>HomeViewModel</code> calls <code>GetSliderImagesUseCase</code> to obtain a stream of images. While waiting, the slider state is set to <code>Loading</code>.
   </td>
   <td>Search for usages of <code>binding.slidersShimmerLayout.visible</code>
   </td>
  </tr>
  <tr>
    <td>2</td>
    <td><code>provideRetrofit</code> calls the REST API on the remote server.</td>
    <td><code>remoteDataSource.requestAllProviders</code></td>
  </tr>
  <tr>
   <td>3</td>
   <td><code>provideRetrofit</code> receives the network response from the remote server.</td>
   <td><code>remoteDataSource.requestAllProviders</code></td>
  </tr>
  <tr>
   <td>4</td>
   <td>
     When <code>HomeViewModel</code> receives the response slider resources it updates the home state to <code>Success</code>.
    <code>HomeFragmnt</code>then uses the response resources in the <code>sliders</code> state to render the screen.
   </td>
   <td>Search for instances of <code>setupSliders</code>
   </td>
  </tr>
</table>

## UI Layer

The [UI layer](https://developer.android.com/topic/architecture/ui-layer) comprises:



*   UI elements built using XML (View System)
*   [Android ViewModels](https://developer.android.com/topic/libraries/architecture/viewmodel)

The ViewModels receive streams of data from use cases and repositories and transform them into UI state. The UI elements reflect this state, and provide ways for the user to interact with the app. These interactions are passed as events to the ViewModel where they are processed.


![Diagram showing the UI layer architecture](docs/images/architecture-4-ui-layer.jpeg "Diagram showing the UI layer architecture")

