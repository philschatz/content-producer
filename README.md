# Create a baked pdf for a new book

1. Run `docker-compose run --rm -e HOST=katalyst01.cnx.org fetch-book --with-resources intro-business` to download the cnxml from the server.
   - **Note:** To see the list of books available see `./books.txt`
1. Run `docker-compose run --rm assemble-book intro-business` to create the single-file HTML for the book.
   - Exercises are fetched when assembling the book. If the book has exercises that are being fetched from the exercises db, it can take 20+ minutes when first assembling a book. After the first time, it should not take as long
1. Run `docker-compose run --rm bake-book intro-business` to convert the single-file HTML locally into the "baked" book.
1. Run `docker-compose run --rm mathify-book intro-business` to convert all the math to svg.
1. Run `docker-compose run --rm build-pdf intro-business` to create the pdf.
