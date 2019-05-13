# NoSQL

## Database Design

* Keep the idea of 'locality' by reference top of mind.
  * It speaks about clustering data that relates to each other close to each other.
  * Often times this means keeping all data in a single table.
* Related items can be grouped together and queried efficiently if their key design causes them to sort together.
* Spread out the volume of queries across the database/dataset.
  * Data keys should distribute traffic across the partitions.
  * Ultimatly this avoids hot spots from happening where all access occurs on one side of the app.
* Specific global secondary indexes, you can enable different queries than your main table can support.
  * This also means that knowing the size of the data up front will assist on partitioning the data.
* Design the shape of the data depending on the shape of the request.
  * This is easy when we think of the GraphQL layer. This is the shape we want to mimic.
