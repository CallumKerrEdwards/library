# library

A very basic library app, using a microservices model.

## Aims

- Build a library app for tracking book ownership in different formats
- Serve digital books and audiobooks
- Manage book metadata

## To-do list

- [x] Build basic books API
- [x] Build read-only web client
- [x] Build gateway to proxy services
- [x] Create basic deployment with Docker Compose
- [ ] Create Kuberentes deployment
- [ ] Create authentication service and handle authentication properly
- [ ] Create content management service to handle book covers

## Deployment

To deploy the latest components, check out this repository and run:

```
docker compose up --wait
```

## Components

- <https://github.com/CallumKerrEdwards/library-api> contains the book API
- <https://github.com/CallumKerrEdwards/library-client> contains the web client
- <https://github.com/CallumKerrEdwards/library-gateway> contains the gateway