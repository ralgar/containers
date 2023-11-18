# 389ds Opinionated Container

I created this container simply because other offerings consistently proved
 problematic for me. I not only wanted to create something more reliable, but
 something that was better suited for deployment to Kubernetes.

## Configuration

### Environment Variables

| Variable Name | Description | Default Value | Required |
|---------------|-------------|---------------|----------|
| DS_SUFFIX_NAME|             | NULL          |          |

ENV DS_DM_PASSWORD
ENV DS_MEMORY_PERCENTAGE
ENV DS_REINDEX
ENV SUFFIX_NAME
ENV DS_STARTUP_TIMEOUT

## Acknowledgements

William Brown and the University of Adelaide - For the original `Dockerfile`
 and `dscontainer` script, both of which I've modified to suit my purposes.
