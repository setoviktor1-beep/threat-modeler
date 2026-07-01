# Demo: Threat-Modeler

**User Request:** "Audit this AWS S3 Terraform bucket:
```hcl
resource 'aws_s3_bucket' 'data' {
  bucket = 'unencrypted-bucket'
  acl    = 'public-read'
}
```"

---

### STRIDE Threat Matrix
| Risk ID | STRIDE Category | Resource | Vulnerability | CVSS Score | Mitigation |
| :--- | :--- | :--- | :--- | :--- | :--- |
| SEC-01 | Information Disclosure | `aws_s3_bucket.data` | Publicly readable bucket. | 8.2 | Restrict access and block public policy. |

### Remediation Patch
```diff
resource "aws_s3_bucket" "data" {
  bucket = "unencrypted-bucket"
- acl    = "public-read"
}
+resource "aws_s3_bucket_public_access_block" "block" {
+  bucket = aws_s3_bucket.data.id
+  block_public_acls = true
+  block_public_policy = true
+}
```
