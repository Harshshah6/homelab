Set cors policy to the bucket

```bash
aws s3api put-bucket-cors --bucket testbucket --endpoint-url https://s3.harshbits.com --cors-configuration cors.json
```