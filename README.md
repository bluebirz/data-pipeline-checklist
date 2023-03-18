
# data-pipeline-checklist

Checklist when create a new data pipeline

- [ ] Endpoints
  - [ ] source
  - [ ] sink
- [ ] Data privacy
  - [ ] PII data
  - [ ] Sensitive information
- [ ] Data security
  - [ ] Hash (e.g. SHA256)
  - [ ] Encryption
    - [ ] Field-level encryption (e.g. AES-GCM, AES-CBC)
    - [ ] File-level encryption (e.g. GPG, PGP)
- [ ] Time-based integration
  - [ ] Batch
    - [ ] schedule time
  - [ ] Near real-time
  - [ ] Real-time
- [ ] Constraints
  - [ ] Rate limits
- [ ] Credentials
  - [ ] User accounts
  - [ ] Service accounts
- [ ] Monitoring
  - [ ] Push notification
  - [ ] Email notification
- [ ] Post-productions
  - [ ] Historical loads
