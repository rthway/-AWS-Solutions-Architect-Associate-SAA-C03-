# Amazon S3 (Simple Storage Service) - Key notes



## 🔹 **Overview of Amazon S3**

-   **Amazon S3** is a **scalable, durable, and secure object storage** service.
    
-   Stores data as **objects in buckets**.
    
-   Ideal for backups, data lakes, websites, analytics, and archival.
    

----------

## 🔹 **Core Concepts**
|Term| Description |
|--|--|
| **Bucket** | A container for storing objects; globally unique name required.  |
| **Object** | Basic entity stored in S3: consists of data, metadata, and key (filename).  |
| **Key** | The unique identifier for an object within a bucket.  |
| **Prefix** | The folder-like path in the object key (used for organizing data).|
| **Region** | Physical location where buckets and data are stored.  |



----------

## 🔹 **Storage Classes**

|Class| Use Case |
|--|--|
| **Standard** | Frequent access; high durability/availability. |
| **Intelligent-Tiering** | Automatically moves data between tiers based on access.|
| **Standard-IA** | Infrequent access; cheaper storage, higher retrieval cost. |
| **One Zone-IA** | Same as IA but stored in a single AZ. |
| **Glacier** | Archival, retrieval in minutes to hours. |
| **Glacier Deep Archive** | Lowest cost; retrieval in 12+ hours. |

--- 

## 🔹 **Data Management**

-   **Versioning**: Keeps multiple versions of an object (can be enabled per bucket).
    
-   **Lifecycle Policies**: Automate transitions between storage classes and deletions.
    
-   **Replication**:
    
    -   **CRR (Cross-Region Replication)**: Copy to another AWS region.
        
    -   **SRR (Same-Region Replication)**.
        

----------

## 🔹 **Security & Access**

-   **IAM Policies**: Grant permissions to users/groups.
    
-   **Bucket Policies**: Grant cross-account permissions at the bucket level.
    
-   **ACLs (Access Control Lists)**: Legacy method, less recommended.
    
-   **Encryption**:
    
    -   **SSE-S3**: Server-side encryption with Amazon-managed keys.
        
    -   **SSE-KMS**: Server-side encryption with customer-managed keys (via KMS).
        
    -   **SSE-C**: Server-side encryption with customer-provided keys.
        
    -   **Client-side encryption** also available.
        

----------

## 🔹 **Performance & Limits**

-   **Read after write** consistency for new objects.
    
-   **Eventual consistency** for overwrites/deletes (now mostly consistent).
    
-   **Multipart Upload**: For large files (>100MB); required for files >5GB.
    
-   **Max Object Size**: 5TB.
    

----------

## 🔹 **Access Methods**

-   **S3 Console**
    
-   **AWS CLI**
    
-   **AWS SDKs**
    
-   **REST API**
    

----------

## 🔹 **Features**

-   **S3 Object Lock**: WORM (Write Once Read Many) protection.
    
-   **S3 Select**: Query subsets of object data using SQL.
    
-   **S3 Inventory**: List of objects and metadata.
    
-   **S3 Access Points**: Simplify managing access to shared data sets.
    

----------

## 🔹 **Pricing Factors**

-   Storage used
    
-   Number of requests
    
-   Data transfer out
    
-   Storage class
    
-   Lifecycle transitions
    
-   Retrieval (Glacier/Deep Archive)
    
