# 🚌 City of Toronto Transit Data Pipeline (AWS)

A production-ready, secure, and scalable AWS data pipeline for processing City of Toronto transit trip data. Built using Infrastructure as Code (Terraform), AWS Glue, Step Functions, Athena, and RDS to support analytics, reporting, and operational visibility.

> 🔗 **Author**: V. Mathur | [vmathurdev](https://github.com/vmathurdev)  

---

## 📐 Architecture Overview

This solution ingests, transforms, and aggregates trip data from city-operated transit vehicles:

```plaintext
1. Transit CSVs → S3 (Raw)
2. S3 triggers → Step Functions → Glue Crawler
3. Glue Crawler → Updates Glue Catalog
4. Glue ETL → Cleans & transforms data → Writes to S3 as partitioned Parquet
5. Processed Parquet → Queried by Athena
6. Second Glue ETL → Aggregates metrics → Loads to RDS PostgreSQL
7. Dimensional tables → `dim_vehicles`, `dim_routes` for normalized querying
8. Monitoring & alerts → CloudWatch, SNS



---


## References

- GitHub Source Code: [https://github.com/vmathurdev/toronto-transit-data-pipeline](https://github.com/vmathurdev/toronto-transit-data-pipeline)
- Terraform Docs: [https://www.terraform.io/docs](https://www.terraform.io/docs)
- AWS Glue Docs: [https://docs.aws.amazon.com/glue/](https://docs.aws.amazon.com/glue/)
