# App

The `app` is a [Next.js](https://nextjs.org/) web app built with React.


## Routes

| Route | Description |
|---|---|
| `/` | The landing page of the app. If this app had user accounts, this is where unauthorized users would be redirected. |
| `/dashboard` | The main page of the application that allows a user to create and view their links. |


## Future Work

- Add user accounts

  Currently this application does not have any user accounts.  This was done to avoid implementing authentication (authN) and authorization (authZ) in this demo app. This functionality is a necessity if this were to be made into a real world application.

- Add stateful routes

  The main route is `/dashboard`. From this page, the user clicks through their list of links.  If a user wants to share a url to a specific link, they can't because the routes do not update with the selected resource.

  In future work I would reorganize the routes so that `/dashboard` becomes `/links`, and when a specific link is selected, the URL is updated to `/links/:id`. That way the user can share the url to a specific link, they can reload the page to see the latest data, and they can use the forwards and backwards buttons to travel through their page history.

- Improve API requests error handling

  Currently, if an API request fails, the UI is left in a loading state. I would handle a failed request better and notify the user instead of remaining in a loading state.

- Allow `Links` to be edited, deleted

  The API supports editing and deleting a link but the UI does not.  I would add a button to enable this functinoality in the UI.

- Allow users to set the redirect token

  The API supports the user setting their own redirect link token but the UI does not. I would add this field as optional to the link form.

- Allow users to change time windows on reporting

  Currently users can only view visit data grouped by day for a 7 day period. I would update the UI to give the user a few more predefined options (i.e. by hour for the past 24 hours).

- Add model validations

  Right now there are some basic database level validations for a few fields (i.e. `Link.token` must be unique) but that is it. I would add model validations [here](https://github.com/matthewsaunders/link-shortener-api/blob/main/internal/data/links.go#L218) and [here](https://github.com/matthewsaunders/link-shortener-api/blob/main/internal/data/visits.go#L212).
