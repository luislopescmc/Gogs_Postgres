
#### Gogs io e Postgres
docker-compose.yml

```bash
version: "3"

services:
  gogs:
    image: gogs/gogs
    volumes:
      - "gogs_data:/data"
    ports:
      - "2222:22"
      - "3000:3000"
    links:
      - db
    depends_on:
      - db

  db:
    image: postgres
    volumes:
      - "pg_data:/var/lib/postgresql/data"
    ports:
      - "5432:5432"
    environment:
      POSTGRES_DB: gogs
      POSTGRES_USER: gogs
      POSTGRES_PASSWORD: gogs

volumes:
  gogs_data:
  pg_data:`
```