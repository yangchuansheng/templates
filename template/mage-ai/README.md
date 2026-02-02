# Mage AI

Mage AI is a powerful data pipeline orchestration platform that allows you to build, run, and manage modern data pipelines with Python, SQL, or R in a notebook-style interface. It's designed to help teams create production-grade data pipelines with confidence.

## Features

- **Modular Pipelines**: Build pipelines block-by-block using Python, SQL, or R
- **Notebook UI**: Interactive editor for writing and documenting pipeline logic
- **Data Integrations**: Prebuilt connectors to databases, APIs, and cloud storage
- **Scheduling**: Trigger pipelines manually or on a schedule (cron supported)
- **Visual Debugging**: Step-by-step logs, data previews, and error handling
- **dbt Support**: Build and run dbt models directly inside Mage
- **Self-Hosted**: Complete control over your data and pipelines
- **AI Integration**: Built-in support for AI-powered workflows

## Deployment

This template deploys Mage AI with the following components:

- **Mage AI Server**: The main application server
- **PostgreSQL Database**: Persistent storage for pipeline metadata and configuration

### Quick Start

1. Deploy the template from Sealos Cloud
2. Access your Mage AI instance via the provided URL
3. Login with your configured credentials (default: `admin@admin.com` / `admin`)
4. Start building your first data pipeline!

## Configuration

### Environment Variables

The following environment variables can be configured during deployment:

| Variable | Description | Default |
|----------|-------------|----------|
| `ADMIN_EMAIL` | Administrator email address | `admin@admin.com` |
| `ADMIN_PASSWORD` | Administrator password (auto-generated if empty) | Auto-generated |
| `MAGE_SECRET_KEY` | Secret key for Mage (auto-generated) | Auto-generated |
| `JWT_SECRET_KEY` | Secret key for JWT tokens (auto-generated) | Auto-generated |

### Database

Mage AI uses PostgreSQL as its backend database. The template includes:
- PostgreSQL 14.8.0 with pgvector extension support
- 1Gi persistent storage
- Automatic initialization and connection configuration

### Storage

- **Project Data**: Temporary storage for pipeline projects (emptyDir, persists during pod lifecycle)
- **Database**: Persistent volume for metadata storage

## Usage

### Creating Your First Pipeline

1. Log in to Mage AI
2. Click "New pipeline" from the dashboard
3. Choose a template or start from scratch
4. Add blocks to define your pipeline logic
5. Run blocks individually or execute the entire pipeline
6. View logs and data previews in real-time

### Supported Data Sources

Mage AI supports connections to:
- PostgreSQL
- MySQL
- Snowflake
- BigQuery
- Redshift
- AWS S3
- Google Cloud Storage
- Azure Blob Storage
- And many more...

### Scheduling Pipelines

To schedule a pipeline:
1. Open the pipeline settings
2. Configure the trigger schedule (cron expression)
3. Mage will automatically execute your pipeline on schedule

## Resources

### Default Resource Allocation

- **CPU**: 100m request, 1000m limit
- **Memory**: 256Mi request, 2Gi limit

These can be adjusted based on your workload requirements.

## Security

- User authentication enabled by default
- Change the default administrator password immediately after first login
- All secrets stored as Kubernetes Secrets
- Network policies enforced by Sealos

## Support

- **Official Documentation**: https://docs.mage.ai
- **GitHub Repository**: https://github.com/mage-ai/mage-ai
- **Community**: https://www.mage.ai/chat
- **Issues**: https://github.com/mage-ai/mage-ai/issues

## License

Apache-2.0 License

## Notes

- This is the open-source version of Mage AI (Mage OSS)
- For enterprise features, consider upgrading to Mage Pro
- The database will be automatically initialized on first deployment
- Pipeline project data is stored in temporary storage and will be lost if the pod is restarted. For production use, configure persistent storage as needed.
