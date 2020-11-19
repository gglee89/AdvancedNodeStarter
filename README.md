# AdvancedNodeStarter

Starting project for a course on Advanced Node @ Udemy

# Server Setup

![image](https://user-images.githubusercontent.com/73807485/99351166-55f8fb80-28e3-11eb-9256-8c31a6c4e46c.png)

# Database

Not having the attribute 'title' indexed, have us not to enjoy any FAST LOOKUP of DATA inside our collection.
![image](https://user-images.githubusercontent.com/16644017/99629782-f41fc980-2a7b-11eb-9da8-a85ebdd7b63f.png)

> We can very easily write queries that don't match up with an index or don't have an index available. In those situations we would very easily run into big performance concerns around our application.

There's two ways to solve this performance concern:

1. Add in an index for that given field; We can have multiple indeces for a given collection. However, whenever we add indices to a collection, that has an impact on our ability to write to that collection. In other words, for every additional index we add to a collection, it takes longer to write records into that collection. In addition any time we add in more indices, that consumes more disk space and more memory as well. So maybe we start making blog post records that have like 30 or 40 different properties tied to them, and we might have to always be looking for different combinations of these properties and we can't figure out ahead of time what indices we would need for that. In all of those situations, the whole idea of using indices to solve these performance problems kinda go out the window, and we have to figure out some different solution.
2. Using a **Caching Layer**.
   ![image](https://user-images.githubusercontent.com/16644017/99639523-0b19e800-2a8b-11eb-990f-d3913c99a58e.png)

> Anytime mongoose issues a query it's going to first go over to this cash server. If it hasn't then the server will take the query, it's going to send it over to MongoDB and Mongo is going to execute the query. We then take the results of that query. It then goes back to the cash server. The cash server is then going to store the result of that query on itself. It's going to say OK, anytime I execute that query I get this response. So it's going to maintain a record between queries that are issued and responses that come back from those queries the server will then take that response and send it back to mongoose, mongoose will give that data to express and it eventually ends up inside of our application.

# Author

**Stephen Grider**  
Udemy.com

**Giwoo G Lee**  
App Development
