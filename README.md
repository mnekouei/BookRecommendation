n this notebook, we will build a book recommendation system based on a simple principle: books with Wikipedia pages that link to similar Wikipedia pages are similar to each other. In order to create this representation of similar books, we'll use the concept of neural network entity embeddings, mapping each book and each Wikipedia link (Wikilink) to a 50-number vector.

The idea of entity embeddings is to map high-dimensional categorical variables to a low-dimensional learned representation that places similar entities closer together in the embedding space. If we were to one-hot-encode the books (another representation of categorical data) we would have a 37,000 dimension vector for each book, with a single 1 indicating the book. In a one-hot encoding, similar books would not be "closer" to one another. By training a neural network to learn entity embeddings, we not only get a reduced dimension representation of the books, we also get a representation that keeps similar books closer to each other. Therefore, the basic approach for a recommendation system is to create entity embeddings of all the books, and then for any book, find the closest other books in the embedding space. Fortunately, thanks to a previous notebook, we have access to every single book article on Wikipedia, which will let us create an effective recommendation system.
