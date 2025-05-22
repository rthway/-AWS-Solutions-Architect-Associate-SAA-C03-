



## Module 2: Knowleadge check

**Q1. Which is the best definition of cloud architecture?**


- [ ]  Designing applications in cloud-based, shared IT infrastructure by using virtual machine and fault-tolerance data storage in the cloud.

- [ ] Relocating traditional on-premises data centers to internet accessible data centers that vendor manages.

- [ ] Combining frontend and backend software and components to create highly available and scalable web services that meet the needs of an organization.

- [ ] Appling cloud characteristics to a solution that uses cloud services and features to meet technical and business requirement.

**✅ Appling cloud characteristics to a solution that uses cloud services and features to meet technical and business requirement.**

**Q2. The AWS well-architected Framework has six pillars. Three of the pillars are security, operational excellence and sustainability what are the two of the other pillars of the WA Framework? Select Two.**

- [ ] Governance

- [ ] Privacy

- [ ] Risk Management

- [ ] Cost optimization

- [ ] Reliability

**✅ Cost optimization.**

**✅ Reliability.**

**Q3. Which actions are consistent with the operational excellence pillar of the AWS well architected framework? (Any two)**

- [ ] Ensure operations personal document changes to the infrastructure.

- [ ] Plan and manage the full lifecycle of hardware assets.

- [ ] Evaluate organizational structures and roles to identify skill gaps.

- [ ] Review and improve process and procedures on a continuous cycle.

- [ ] Apply software engineering principles and methodology to infrastructure as code.

**✅ 1. Review and improve processes and procedures on a continuous cycle.**

**Why:**  
This directly aligns with the **Operational Excellence** pillar, which emphasizes **continuous improvement**. One of the design principles of this pillar is to **“evolve procedures over time to improve operations”**. Regularly reviewing and refining operational procedures ensures the system remains efficient, reliable, and adaptable.

**✅ 2. Apply software engineering principles and methodology to infrastructure as code.**

**Why:**  
This supports the Operational Excellence goal of **automating changes, tracking versions, and reducing human error**. By using **Infrastructure as Code (IaC)**, teams can manage infrastructure in a repeatable, testable, and automated way — promoting consistency, speed, and reliability. These are core goals of operational excellence.

----------

**❌ Incorrect options (and why):**

-   **Ensure operations personnel document changes to the infrastructure**  
    → While documentation is important, this is more of a **governance** or **change management** concern, not a core practice uniquely emphasized by Operational Excellence.
-   **Plan and manage the full lifecycle of hardware assets**  
    → This is related to **hardware management**, which is more applicable to the **Cost Optimization** or **Sustainability** pillars, especially in hybrid or on-prem environments.
-   **Evaluate organizational structures and roles to identify skill gaps**  
    → This is an **HR/training and development** focus, aligning more with **people management** and not a direct technical practice within Operational Excellence.

**Q4. A specific application requires a frontend web tier of multiple servers that communicate with a backend application tier of multiple servers. Which design most closely follows AWS best practices.**

- [ ] Create multiple instances that each combine a web frontend and application backend in same instance.

- [ ] Create a full mesh network between the web and application tires, so thar each web server can directly communicate with every application tier

- [ ] Assign a dedicate application server and dedicated connection to each web server

- [ ] Design the web tier to communicate with the application tier through the Elastic Load Balancing (ELB) Service.

**✅ Design the web tier to communicate with the application tier through the Elastic Load Balancing (ELB) Service.**

**Q5. A solution architect is developing a process for handling server failures. Which process most closely follows AWS best practices.**

- [ ] The operations staff detects a system failure. They notify the system administrator, which provisions a new server by using the AWS management console.

- [ ] Amazon CloudWatch detects a system failure. It notifies the system administrator who provisions a new server by using the AWS management console.

- [ ]   Amazon cloudWatch detects a system failure. It initiates automation to provision a new server

- [ ] The operations staff detect a system failure. They initiate automation to provision a new server

**✅ Amazon cloudWatch detects a system failure. It initiates automation to provision a new server.**

**Q6. A company is considering moving their on-premises data center to the cloud. Their primary motivation is to increase their cost efficiency. Which approach most closly follows AWS best practices.**

- [ ] Provision the server that are needed and stop service when they are not being used.

- [ ] Replicate their on-premises data center in the cloud.

- [ ] Maintain the on-premise data center as long as possible.

- [ ] Provision some of ther servers in the cloud and ensure the servers run 24/7.

**✅ Provision the server that are needed and stop service when they are not being used.**

**Q7. A company stores read-only data in amazon S3. Most users are in the same country as the company headquarters. Some users ae located around the world. Which design discission most closely follows AWS best practices.**

- [ ] Use a bucket in the AWS region that is closest to the company headquarters. All users access the data through Amazon CloudFront.

- [ ] Replicate objects across buckets in AWS regins around the world. Users access the bucket in the region closer that is to them.

- [ ] Use a bucket in the region that has lowest average latency for all users.

- [ ] Use a bucket in the region that has the lowest average latency for all users.

- [ ] Use a bucket in the region closest to the company headquarters.

**✅ Use a bucket in the AWS region that is closest to the company headquarters. All users access the data through Amazon CloudFront.**

**Q8. A consultant must access a large object in an S3 bucket. They need one day to access the file. Which method for gaming access most closely follows AWS practices?**

- [ ] Copy the object to a new S3 bucket. Enable public access on the new bucket. From the new bucket, get the object URL, and Give it to the consultant.

- [ ] Enable public access on the S3 bucket. Give the URL to the consultant.

- [ ] Create a presigned URL to the object that expires in 24 hours, and give it to the consultant.

- [ ] Create a user account for the consultant. Grant the user account permission to access the S3 bucket through the AWS Management Console.

**✅ Create a presigned URL to the object that expires in 24 hours, and give it to the consultant.**

**Q9. Which are main considerations that influence which AWS regions to use? ANY TWO?**

- [ ] Application resiliency during system failures.

- [ ] Latency reduction for end users.

- [ ] Security and access control.

- [ ] Compliance with laws and regulations.

- [ ] Protection against localized natural disaster.

**✅ Latency reduction for end users.**

**✅ Compliance with laws and regulations**

**Q10. Which are main considerations that influence which Availability Zones to use? ANY TWO?**

- [ ] Application resiliency during system failures.

- [ ] Latency reduction for end users.

- [ ] Security and access control.

- [ ] Compliance with laws and regulations.

- [ ] Protection against localized natural disaster.

**✅ Application resiliency during system failures**

**✅ Protection against localized natural disaster.**
