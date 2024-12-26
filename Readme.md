Use as following in docker compose file:
TODO = add example init.sh...
postgres_init:
    image: ghcr.io/phaf4it/docker-pg-client:main
    environment:
      PGDATABASE: database
      PGHOST: postgres
      PGPORT: 5432
      PGUSER: postgres
      PGPASSWORD: postgres
    working_dir: /scripts
    networks:
      - db
    volumes:
      - ./docker/database/scheme/postgres:/scripts/
    depends_on:
      - postgres
    command:
      - "insert.sh"
