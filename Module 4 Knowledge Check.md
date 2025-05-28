# Module 4 Knowledge Check
**Q1. Due to a company manager, a data engineer needs to  increase their their object storage capacity. They are not sure how much stroage they will need. They want a highly scalable service that can store unstructured, semistructed and structures data. Which service would be the most cost effective to accompish this task?**
- [ ]  Amazon S3
- [ ] Amazon Elastic Block Store (Amazon EBS)
- [ ] AWS Stroage Gateway
- [ ] Amozen RDS

**✅ Amazon S3** 

**Q2. Amazon S3 provides a good solution for which use case?**
- [ ]  Hourly stroage of frequently accessed temporary data.
- [ ] An internet-accessible stroage location for video files that an external website can access.
- [ ] Ledger data that is updates and accessed frequently.
- [ ] A data warehouse for business intelligence. 

**✅ An internet-accessible stroage location for video files that an external website can access.** 

**Q3. A company is intrested in using Amazon s3 to host their website instead of a traditional web server. which type of content does Amazon S3 support for static web hosting.(Select THREE)**
- [ ]  Video and sound files
- [ ] Database engine
- [ ] Server-side scripts
- [ ] Client-side scripts
- [ ] HTML files and inmage files
- [ ] Dynamic HTML files

**✅ Video and sound files** 
**✅ HTML files and inmage files** 
**✅ Client-side scripts** 

**Q4. A company wants to use an S3 bucket to store sesetive data. Which Actions can they take to protect their data? (Select TWO)**
- [ ]  Using client-side encryption t protect data in trasit before it is sent to Amazon S3.
- [ ] Using Secure File Transfer Protocal (SFTP) to connect directly to Amazon S3.
- [ ] Uploading unencrypted files to Amazon S3 because Amazon S3 encrypts the files by default.
- [ ] Enabling Server-side encryption on the S3 bucket before uploading sensitive data.
- [ ] Enabling Server-side encryption on S3 bucket afet uploading sensetive data.

**✅ Using client-side encryption t protect data in trasit before it is sent to Amazon S3.**
**✅ Enabling Server-side encryption on the S3 bucket before uploading sensitive data.**  

**Q5. A company must create a common place to store shared files. which requirements does Amazon S3 support? (Select TWO)**
- [ ]  Lock the file so that only one person at a time can edit it.
- [ ] Attach comments to file.
- [ ] Recover deleted data. 
- [ ] Compare file contents between files.
- [ ] Maintaion different versions of files.

**✅ Recover deleted data.** 
**✅ Maintaion different versions of files.** 


**Q6. A customer service team accesses case data daily for up to 30 days. Cases can be responded and require immidate access for 1 year after they are closed. Reopened cases required 2 days to process Which solution meets the requirement and it the most cost effective?**
- [ ]  Store all data in S3 standard so that it is available whenever needed.
- [ ] Store case data in S3 Standard. Use a lifecycle policy to move the data into S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days.
- [ ] Store case data in S3 Standard. Use a lifecycle policy to move the data into Amazon S3 Glacier after 30 days.
- [ ] Store case data in S3 intelligent-Tiering to automatically move data between tier based on access frequntly.

**✅ Store case data in S3 Standard. Use a lifecycle policy to move the data into S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days.** 

**Q7. Which option takes advantage of edge locations in Amazon CloudFront to transfer files over long distances to an S3 bucket?**
- [ ]  Amazon S3 Transfer Acceration.
- [ ] AWS SDKs
- [ ] AWS Transfer Family
- [ ] Amazon S3 REST API

**✅ Amazon S3 Transfer Acceration.** 

**Q8. A video producer must regularly transfer sevral video files to amazon S3. The files range from 100-700 MB. The internet connection has been unreliable, causing some uploaded to fails. which solutions provides the fasted, most reliable and most cost effective way to transfer these files to Amazon S3?**
- [ ]  Aws Managment Console
- [ ] Amazon S3 multipart uploaded
- [ ] Amazon S3 Transfer Acceleration
- [ ] AWS Transfor Family. 

**✅ Amazon S3 multipart uploaded** 

**Q9. Which Amazon S3 stroage class is designed for backup copies of on-premises data or easily re-creatable data?**
- [ ]  S3 One Zone-Infrequent Access (S3 One Zone-IA)
- [ ] S3 Intellaigent-Tiering
- [ ] S3 Standard-Infrequent Access (S3 Standard-IA)
- [ ] S3 Glacier Instant Retrival


**✅ S3 One Zone-Infrequent Access (S3 One Zone-IA)** 

**Q10. A company needs to retain record for regulatory purpose for a 7-years peroid. These records are rarely accessed (Once or Twice a year). What is the lowest-cost storage class for Amazon S3?**
- [ ]  Glacier Deep Archive
- [ ] S3 Intelligent-Tiering
- [ ] S3 Standard-Infrequent Access (S3 Standard-IA)
- [ ] S3 One Aone-Infrequent Access (S3 One Zone-IA)

**✅ Glacier Deep Archive** 
