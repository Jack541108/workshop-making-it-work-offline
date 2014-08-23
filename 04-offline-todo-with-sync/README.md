# Offline todo with IndexedDB with synchronisation

We will now enhance our simple offline-first to-do application by hooking it up to a server so that, when it has an internet connection, it can synchronise its data.  Here is what the app will do:

- everything that the previous app did, on as many browsers;
- synchronises its todos with the server, deleting todos on the server that have been deleted locally, added todos on the server that have been created locally.

## Prerequisites

As this is a front end course we're going to use a backend that I've already prepared.  If you are using a computer that has Node (v0.10+) installed then download, install and run **[offline todo api](https://github.com/matthew-andrews/offline-todo-api)**.

```
npm install -g offline-todo-api
offline-todo-api
```

Otherwise, deploy the **[offline todo api](https://github.com/matthew-andrews/offline-todo-api)** project to a new (free) Heroku app.

Verify that your server is running correctly by going to `http://localhost:3000/todos` (replacing `http://localhost:3000` as appropriate) and checking that JSON encoded array is returned.  (At this stage it's probably empty - `[]`)