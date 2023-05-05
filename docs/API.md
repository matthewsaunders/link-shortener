# Api

The `api` is a JSON API written in golang to support the `shrtnr` web app.

## Routes

| Verb | Route | Description |
|---|---|---|
| GET | /v1/healthcheck | Healtchcheck route to confirm the API is up and running |
| GET | /v1/links | Return a list of `Link` records |
| POST | /v1/links | Create a new `Link` record |
| GET | /v1/links/:id | Get a `Link` record |
| PATCH | /v1/links/:id | Update a `Link` record |
| DELETE | /v1/links/:id | Delete a `Link` record |
| GET | /v1/links/:id/visits | Get visit data for a `Link` record |
| GET | /v1/tokens/new | Get a new unique `Link` token (i.e. `abc123`) |
| GET | /a/:token | Redirect the user for a given token |


### Future work

- Add user accounts (authZ and authN)

  User accounts are manadtory if this app were to be deployed in the real world. Then, the API would use [JSON Web Tokens](https://jwt.io/) to authenticate users (authN), and all resources could be protected by user authorization (authZ).

- Allow users to change time windows on reporting

  The time frame used in the queries for the `/v1/links/:id/visits` endpoint are statically defined to group by day for a 7 day period. In future work I would allow users to use queries parameters to change the period and duration of group data.

- Collect more information from visits

  Right now a `Visit` record only captures that a visit happened and when it happened. In future work I would capture more data (i.e. referrer, location, utm tags or other query params). I would also build reporting for this information in the web app.
