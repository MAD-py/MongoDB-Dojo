# **Dojo**

<p align="center">
<img src="https://seeklogo.com/images/M/mongodb-logo-427DDF8FDE-seeklogo.com.png" width="70%">
</p>

**MongoDB** is an open source database NoSQL that uses a document-oriented data model and a semi-structured query language. This database is written in **C++**.

## What is NoSQL?

NoSQL ("non SQL" or "not only SQL") is an approach to database design that enables the storage and querying of data outside the traditional structures found in relational databases. In a NoSQL database, data is stored in an unstructured form mainly as key-value.

### Type of NoSQL database

1. **Key-Value store**:
    It's a typical NoSQL database that stores data as key-value pairs, where each element has a key that's unique in the set of data, while the value is an array of data. 

    Some examples of this type of database are Redis and Memcached that are open source.

2. **Wide-Column store**:
    This type of database store information in columns, enabling users to access only the specific columns they need. This database tries to solve for the shortcomings of key-value and document store.

    Some examples of this type of database are Apache HBase and Apache Cassandra that are open source.

3. **Graph store**:
    This type of database stores all its data in a graph, each piece of data is stored as a node of the Graph and its relations to other nodes is established by means of the graph edges. Although this type of database talks about relations, it is still NoSQL because it is unstructured data.

    An example of such a database is Neo4j which is open source and built on java.

4. **Document store**:
    As suggested by the name of this type of database, the data is stored in documents that typically use XML, JSON or BSON formats to store the information in a semi-structured form, making it easy to access and not having to respect any particular data structure between documents.

    An example of such a database is **MongoDB** which is open source.

## Decomposing **MongoDB**

The internal architecture of **MongoDB** is built on the concept of collections and documents. The most atomic unit is a set of key-value pairs that allows documents to have different fields between them. The format used by **MongoDB** in its documents is [BSON](https://bsonspec.org) which is a binary representation of the traditional [JSON](https://www.json.org/json-en.html) format.

### Architecture

* *Database*: It is the physical container for the data. Each database has its own set of files on the file system and multiple databases can exist on a single **MongoDB** server.

* *Collection*: It is a group of documents that are intended for the same purpose. All collections exist within a single database and there are no defined schemas in these.

* *Document*: A set of key-value pairs that is called a document. Documents are composed of dynamic schemas that allow the same collection to contain documents with different structures.

<p align="center">
</br>
<img src="https://www.pragimtech.com/blog/contribute/article_images/2220211210231003/mongodb-collection-vs-document.jpg" width="60%">
</p>

<p align="center">
(Source: <a href="https://www.pragimtech.com/blog/mongodb-tutorial/relational-and-non-relational-databases/">Pragimtech MongoDB Tutorial</a>)
</p>


**MongoDB** is very flexible and allows you to combine and store multivariate data without compromising the powerful indexing, fast data access and validation rules it has.

### Advantages

* No downtime while the application is being scaled
* Performs in-memory processing
* Text search
* Multiple Servers
* Graph processing
* Global replication
* Economical

## Install **MongoDB**

**MongoDB** can be installed on the following platforms.

### **Linux**

Install dependecies:

```bash
sudo apt update
sudo apt install dirmngr gnupg apt-transport-https ca-certificates software-properties-common
```

Add **MongoDB** GPG key:

```bash
sudo wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | sudo apt-key add -
```

Create a list for **MongoDB**:

```bash
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
```

Update package:

```bash
sudo apt update
```

Install **MongoDB**:

```bash
sudo apt install mongodb-org
```

### **macOS**

Tap **MongoDB** Homebrew:

```bash
brew tap mongodb/brew
```

Update Homebrew:

```bash
brew update
```

Install **MongoDB**:

```bash
brew install mongodb-community@6.0
```
### **Docker**

Pull image:

```bash
sudo docker pull mongo
```

Run image:

```bash
docker run --name some-mongo -d mongo
```

## **MongoDB** Atlas

[**MongoDB** Atlas](https://www.mongodb.com/cloud/atlas/register) is a cloud clustering service that supports multiple providers such as AWS, Azure and GCP, with Atlas you can have a **MongoDB** cluster in a few steps and leaving aside all kinds of worries about hardware and software upgrades.

## Drivers

Using **MongoDB** is easy with its officially drivers and libraries. In this dojo in the [languages](./languages/README.md) folder you can find a practical example of how to use **MongoDB** with Python, Nodejs, go and **MongoDB** Shell.

Other languages officially supported by **MongoDB**:
* [C](https://www.mongodb.com/docs/drivers/c/)
* [C++](http://mongocxx.org)
* [C#](https://www.mongodb.com/docs/drivers/csharp/current/)
* [Java](https://www.mongodb.com/docs/drivers/java/sync/current/)
* [PHP](https://www.mongodb.com/docs/drivers/php/)
* [Ruby](https://www.mongodb.com/docs/mongoid/current/#mongoid)
* [Rust](https://www.mongodb.com/docs/drivers/rust/)
* [Scala](https://www.mongodb.com/docs/drivers/scala/)
* [Swift](https://mongodb.github.io/mongo-swift-driver/docs/current/MongoSwift/index.html)

## **MongoDB** Compass

**MongoDB** Compass is a powerful GUI for querying, aggregating, and analyzing your **MongoDB** data in a visual environment.

Compass is free to use and source available, and can be run on macOS, Windows, and Linux.

### **Linux**

Download:
```bash
wget https://downloads.mongodb.com/compass/mongodb-compass_1.35.0_amd64.deb
```

Install:
```bash
sudo dpkg -i mongodb-compass_1.35.0_amd64.deb
```

### **Windows** and **macOS**

On the official **MongoDB** [website](https://www.mongodb.com/try/download/compass) you will find the executables to install on Windows and macOS.
