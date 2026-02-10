# Big-Health-Data-DB-Research
Database Model Research for Big Health Data Analysis 

## Project Description
As the healthcare industry shifts toward digital data management, the sheer volume and variety of health data present a significant challenge for traditional storage systems. Health data is predominantly textual, semi-structured, and document-oriented, requiring a high frequency of read/write operations for effective analysis.

This project investigates the effectiveness of different database models for big health data. The goal was to determine whether a traditional Relational Database (SQL Server) or a Document-Oriented Database (MongoDB) provides better scalability and efficiency. Specifically, looking into the benefits of MongoDB Sharding, a feature that distributes data across multiple machines in a cloud environment to handle massive datasets.

## Key Findings
To evaluate performance, SQL Server, MongoDB (Standalone), and MongoDB (Sharded) were compared across four queries of varying complexity.

### Write Operations
- MongoDB (Standalone) was the clear winner for writing large volumes of health data.
- MongoDB (Sharded) showed a slight performance hit during writes compared to the standalone version, due to the overhead of distributing data across a cloud environment.

### Read Operations & Scalability
- Small Datasets: SQL Server initially outperformed both MongoDB configurations in read tasks.
- Large Datasets (1M+ Records): As data scaled, the MongoDB Sharded configuration became the most efficient model. It significantly outperformed standalone MongoDB and matched or exceeded SQL Server's performance for complex read operations.

### Development Flexibility
- Unlike SQL, which requires a rigid relational schema and time-consuming normalization, MongoDB's schema-less nature allows for rapid development. This flexibility is critical for health data, which often changes structure depending on the source.


## Reflection
Choosing a database for health data isn't just about raw speed; it’s about balancing flexibility and scalability. While SQL is reliable for smaller, highly structured datasets, it lacks the agility needed for the "persistent expansion" of modern medical records.

In my opinion, the transition from SQL to NoSQL is highly beneficial for organizations dealing with Big Data. Although sharding introduces some latency in write operations, the trade-off for superior read performance at scale is worth it for analyzing big health data.

### Future Considerations:
- Security: Health data is highly sensitive. Future iterations of this model must incorporate robust security layers to ensure HIPAA compliance and data privacy in the cloud.
- Processing Models: Integrating Map-Reduce or other modern data processing tools could further optimize how insights are extracted from these large datasets.

## References
- Goli-Malekabadi, Z., Sargolzaei-Javan, M., & Akbari, M. K. (2016). An effective model for store and retrieve big health data in cloud computing. Computer Methods and Programs in Biomedicine, 132(1), 75-82. http://dx.doi.org/10.1016/j.cmpb.2016.04.016
- MongoDB, Inc. (n.d.). Sharding in MongoDB. https://www.mongodb.com/basics/sharding
