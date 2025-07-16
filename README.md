In this project, let's build **Nxt Watch** by applying the concepts we have learned till now.

### Refer to the videos below:

**Success View** <br/>

<div style="text-align: center;">
     <video style="max-width:80%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12);outline:none;" loop="true" autoplay="autoplay" controls="controls" muted>
    <source src="https://assets.ccbp.in/frontend/content/react-js/nxt-watch-output-v0.mp4" type="video/mp4">
  </video>
</div>
<br/>

**Failure View** <br/>

<div style="text-align: center;">
    <video style="max-width:80%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12);outline:none;" loop="true" autoplay="autoplay" controls="controls" muted>
    <source src="https://assets.ccbp.in/frontend/content/react-js/nxt-watch-failure-output-v0.mp4" type="video/mp4">
  </video>
</div>
<br/>



<summary>Functionality to be added</summary>
<br/>

The app must have the following functionalities

- Initially, the app should be in **Light** theme

- **Login Route**

  - When invalid credentials are provided and the **Login** button is clicked, then the error message received from the response should be displayed
  - When valid credentials are provided and the **Login** button is clicked, then the page should be navigated to the Home Route
  - When an _unauthenticated_ user tries to open the Home, Trending, Gaming, Saved Videos, and Video Details Route, then the page should be navigated to the Login Route
  - When an _authenticated_ user tries to open the Home, Trending, Gaming, Saved Videos, and Video Details Route, then the page should be navigated to the respective route
  - When an _authenticated_ user tries to open the Login Route, then the page should be navigated to the Home Route
  - When the **Show Password** checkbox is checked, then the password should be shown
  - When the **Show Password** checkbox is unchecked, then the password should be masked

- **Home Route**

  - When an _authenticated_ user opens the Home Route,
    - An HTTP GET request should be made to the **Home Videos API URL** with `jwt_token` in the Cookies and query parameter `search` with the initial value as an empty string
      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the list of videos should be displayed
      - If the HTTP GET request made is unsuccessful, then the [Failure View](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-home-failure-light-theme-lg-output-v0.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **Home Videos API URL**
    - When a non-empty value is provided in the search input and the search icon button is clicked
      - Make an HTTP GET request to the **Home Videos API URL** with `jwt_token` in the Cookies and query parameter `search` with value as the text provided in the search input
      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the list of videos should be displayed
    - When the HTTP GET request made to the **Home Videos API URL** returns an empty list, then the [No Videos View](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-home-no-videos-light-theme-lg-output-v0.png) should be displayed
  - When a **Video** is clicked, then the page should be navigated to the Video Item Details Route
  - When the **Trending** link in the Sidebar is clicked, then the page should be navigated to the Trending Route
  - When the **Gaming** link in the Sidebar is clicked, then the page should be navigated to the Gaming Route
  - When the **Saved Videos** link in the Sidebar is clicked, then the page should be navigated to the Saved Videos Route

- **Trending Route**

  - When an _authenticated_ user opens the Trending Route,
    - An HTTP GET request should be made to the **Trending Videos API URL** with `jwt_token` in the Cookies
      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the list of videos should be displayed
      - If the HTTP GET request made is unsuccessful, then the [Failure View](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-trending-failure-light-theme-lg-output-v0.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **Trending Videos API URL**
  - When a **Video** is clicked, then the page should be navigated to the Video Item Details Route
  - When the **Home** link in the Sidebar is clicked, then the page should be navigated to the Home Route
  - When the **Gaming** link in the Sidebar is clicked, then the page should be navigated to the Gaming Route
  - When the **Saved Videos** link in the Sidebar is clicked, then the page should be navigated to the Saved Videos Route

- **Gaming Route**

  - When an _authenticated_ user opens the Gaming Route,
    - An HTTP GET request should be made to the **Gaming Videos API URL** with `jwt_token` in the Cookies
      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the list of videos should be displayed
      - If the HTTP GET request made is unsuccessful, then the [Failure View](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-gaming-failure-light-theme-lg-output-v0.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **Gaming Videos API URL**
  - When a **Video** is clicked, then the page should be navigated to the Video Item Details Route
  - When the **Home** link in the Sidebar is clicked, then the page should be navigated to the Home Route
  - When the **Trending** link in the Sidebar is clicked, then the page should be navigated to the Trending Route
  - When the **Saved Videos** link in the Sidebar is clicked, then the page should be navigated to the Saved Videos Route

- **Video Item Details Route**

  - When an _authenticated_ user opens the Video Item Details Route
    - An HTTP GET request should be made to the **Video Details API URL** with `jwt_token` in the Cookies and `video_id` as a path parameter
      - **_Loader_** should be displayed while fetching the data
      - After the data is fetched successfully, the response received should be displayed
      - If the HTTP GET request made is unsuccessful, then the [Failure View](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-video-item-details-failure-light-theme-lg-output-v0.png) should be displayed
        - When the **Retry** button is clicked, an HTTP GET request should be made to the **Video Details API URL**
  - Corresponding video should be displayed using `react-player` package
  - Initially, all the three buttons (Like, Dislike, Save) should be inactive
  - When the **Like** button is clicked,
    - It should change to active state
    - If the **Dislike** button is already in the active state, then the **Dislike** button needs to be changed to the inactive state
  - When the **Dislike** button is clicked,

    - It should change to active state
    - If the **Like** button is already in the active state, then the **Like** button needs to be changed to the inactive state

  - When the **Save** button is clicked,
    - It should change to active state and the respective video details should be added to the list of saved videos
    - **Save** button text should be changed to **Saved**
  - When the **Saved** button is clicked
    - It should change to inactive state and the respective video details will be removed from the list of saved videos
    - **Saved** button text should be changed to **Save**

- **Saved Videos Route**

  - When an _authenticated_ user opens the Saved Videos Route,
    - If the list of saved videos is empty, then the [No Saved Videos Found View](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-no-saved-videos-light-theme-lg-output-v0.png) should be displayed
    - The list of saved videos should be displayed
  - When a **Video** is clicked, then the page should be navigated to the Video Item Details Route
  - When the **Home** link in the Sidebar is clicked, then the page should be navigated to the Home Route
  - When the **Trending** link in the Sidebar is clicked, then the page should be navigated to the Trending Route
  - When the **Gaming** link in the Sidebar is clicked, then the page should be navigated to the Gaming Route

- **Not Found Route**

  - When a random path is provided as the URL path, then the page should be navigated to the Not Found Route

- **Header**

  - When the Website logo is clicked, then the page should be navigated to the Home Route
  - When the theme icon button is clicked, then the theme should be changed accordingly
  - When the **Logout** button is clicked, then the [Logout Popup](https://assets.ccbp.in/frontend/content/react-js/nxt-watch-logout-popup-light-theme-lg-output-v0.png) should be displayed
    - When the **Cancel** button is clicked, then the popup should be closed and the page should not be navigated
    - When the **Confirm** button is clicked, then the page should be navigated to the Login Route

</details>






**The following instructions are required for the tests to pass**

- Render `Home` Route component when the path in URL matches `/`
- Render `Login` Route component when the path in URL matches `/login`
- Render `Trending` Route component when the path in URL matches `/trending`
- Render `Gaming` Route component when the path in URL matches `/gaming`
- Render `Saved Videos` Route component when the path in URL matches `/saved-videos`
- Render `Video Item Details` Route component when the path in URL matches `/videos/:id`
- Render `Not Found` Route component when the path in URL matches `/not-found`





- **Home Route**

  - The Route should consist of an HTML container element with `data-testid` as **home**
  - The Route should consist of a banner and it contains a close button with `data-testid` as **close**
  - The Route should consist of a banner as shown in the design files with `data-testid` as **banner**
  - The Route should consist of an HTML image element with alt as **nxt watch logo** and src as the given Nxt Watch logo URL in the banner
  - The HTML container element with `data-testid` as **home** should have the background color,
    - If the Light theme is applied, then the **#f9f9f9** color should be applied as a background color
    - If the Dark theme is applied, then the **#181818** color should be applied as a background color

- **Trending Route**

  - The Route should consist of an HTML container element with `data-testid` as **trending**
  - The HTML container element with `data-testid` as **trending** should persist the background color,
    - If the Light theme is applied, then the **#f9f9f9** color should be applied as a background color
    - If the Dark theme is applied, then the **#0f0f0f** color should be applied as a background color

- **Gaming Route**

  - The Route should consist of an HTML container element with `data-testid` as **gaming**
  - The HTML container element with `data-testid` as **gaming** should persist the background color,
    - If the Light theme is applied, then the **#f9f9f9** color should be applied as a background color
    - If the Dark theme is applied, then the **#0f0f0f** color should be applied as a background color

- **Saved Videos Route**

  - The Route should consist of an HTML container element with `data-testid` as **savedVideos**
  - The HTML container element with `data-testid` as **savedVideos** should persist the background color,
    - If the Light theme is applied, then the **#f9f9f9** color should be applied as a background color
    - If the Dark theme is applied, then the **#0f0f0f** color should be applied as a background color

- **Video Item Details Route**

  - The **Video Item Details** Route should consist of an HTML container element with `data-testid` as **videoItemDetails**
  - The HTML container element with `data-testid` as **videoItemDetails** should persist the background color,
    - If the Light theme is applied, then the **#f9f9f9** color should be applied as a background color
    - If the Dark theme is applied, then the **#0f0f0f** color should be applied as a background color

- The **Website logos** for Light theme and Dark theme should have the alt as **website logo**
- The **Failure** images for Light theme and Dark theme should have the alt as **failure view**
- In the Video Item Details Route, the **#2563eb** color should be applied as `color` for any active button i.e (Like, Dislike, Save)
- In the Video Item Details Route, the **#64748b** color should be applied as `color` for any inactive button i.e (Like, Dislike, Save)

</details>

### Resources

<details>
<summary>Image URLs</summary>

- [https://assets.ccbp.in/frontend/react-js/nxt-watch-logo-light-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-logo-light-theme-img.png)
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-logo-dark-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-logo-dark-theme-img.png)
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-profile-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-profile-img.png) alt should be **profile**
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-failure-view-light-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-failure-view-light-theme-img.png)
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-failure-view-dark-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-failure-view-dark-theme-img.png)
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-no-search-results-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-no-search-results-img.png) alt should be **no videos**
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-no-saved-videos-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-no-saved-videos-img.png) alt should be **no saved videos**
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-not-found-light-theme-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-not-found-light-theme-img.png) alt as **not found**
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-banner-bg.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-banner-bg.png) **banner background image**
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-facebook-logo-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-facebook-logo-img.png) alt should be **facebook logo**
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-twitter-logo-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-twitter-logo-img.png) alt should be **twitter logo**
- [https://assets.ccbp.in/frontend/react-js/nxt-watch-linked-in-logo-img.png](https://assets.ccbp.in/frontend/react-js/nxt-watch-linked-in-logo-img.png) alt should be **linkedin logo**

</details>

<details>
<summary>Colors</summary>

<br/>

<div style="background-color: #0f0f0f; width: 150px; padding: 10px; color: white">Hex: #0f0f0f</div>
<div style="background-color: #f9f9f9; width: 150px; padding: 10px; color: black">Hex: #f9f9f9</div>
<div style="background-color: #f8fafc; width: 150px; padding: 10px; color: black">Hex: #f8fafc</div>
<div style="background-color: #1e293b; width: 150px; padding: 10px; color: white">Hex: #1e293b</div>
<div style="background-color: #f1f5f9; width: 150px; padding: 10px; color: black">Hex: #f1f5f9</div>
<div style="background-color: #475569; width: 150px; padding: 10px; color: white">Hex: #475569</div>
<div style="background-color: #f1f1f1; width: 150px; padding: 10px; color: black">Hex: #f1f1f1</div>
<div style="background-color: #181818; width: 150px; padding: 10px; color: white">Hex: #181818</div>
<div style="background-color: #e2e8f0; width: 150px; padding: 10px; color: black">Hex: #e2e8f0</div>
<div style="background-color: #94a3b8; width: 150px; padding: 10px; color: black">Hex: #94a3b8</div>
<div style="background-color: #4f46e5; width: 150px; padding: 10px; color: white">Hex: #4f46e5</div>
<div style="background-color: #64748b; width: 150px; padding: 10px; color: white">Hex: #64748b</div>
<div style="background-color: #231f20; width: 150px; padding: 10px; color: white">Hex: #231f20</div>
<div style="background-color: #ffffff; width: 150px; padding: 10px; color: black">Hex: #ffffff</div>
<div style="background-color: #212121; width: 150px; padding: 10px; color: white">Hex: #212121</div>
<div style="background-color: #616e7c; width: 150px; padding: 10px; color: white">Hex: #616e7c</div>
<div style="background-color: #3b82f6; width: 150px; padding: 10px; color: white">Hex: #3b82f6</div>
<div style="background-color: #00306e; width: 150px; padding: 10px; color: white">Hex: #00306e</div>
<div style="background-color: #ebebeb; width: 150px; padding: 10px; color: black">Hex: #ebebeb</div>
<div style="background-color: #7e858e; width: 150px; padding: 10px; color: black">Hex: #7e858e</div>
<div style="background-color: #d7dfe9; width: 150px; padding: 10px; color: black">Hex: #d7dfe9</div>
<div style="background-color: #cbd5e1; width: 150px; padding: 10px; color: black">Hex: #cbd5e1</div>
<div style="background-color: #000000; width: 150px; padding: 10px; color: white">Hex: #000000</div>
<div style="background-color: #ff0b37; width: 150px; padding: 10px; color: white">Hex: #ff0b37</div>
<div style="background-color: #ff0000; width: 150px; padding: 10px; color: white">Hex: #ff0000</div>
<div style="background-color: #383838; width: 150px; padding: 10px; color: white">Hex: #383838</div>
<div style="background-color: #606060; width: 150px; padding: 10px; color: white">Hex: #606060</div>
<div style="background-color: #909090; width: 150px; padding: 10px; color: black">Hex: #909090</div>
<div style="background-color: #cccccc; width: 150px; padding: 10px; color: black">Hex: #cccccc</div>
<div style="background-color: #424242; width: 150px; padding: 10px; color: black">Hex: #424242</div>
<div style="background-color: #313131; width: 150px; padding: 10px; color: black">Hex: #313131</div>
<div style="background-color: #f4f4f4; width: 150px; padding: 10px; color: black">Hex: #f4f4f4</div>
<div style="background-color: #424242; width: 150px; padding: 10px; color: black">Hex: #424242</div>

</details>

<details>
<summary>Font-families</summary>

- Roboto

</details>

> ### _Things to Keep in Mind_
>
> - All components you implement should go in the `src/components` directory.
> - Don't change the component folder names as those are the files being imported into the tests.
> - **Do not remove the pre-filled code**
> - Want to quickly review some of the concepts you’ve been learning? Take a look at the Cheat Sheets.
