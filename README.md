# PDS Portal

This is the parent repository for the NASA Planetary Data System (PDS) portal ecosystem. It serves as the central location for tracking update requests, tasks, and issues related to the pds.nasa.gov website.

## Purpose

This repository is used to track update requests for the pds.nasa.gov website. The actual code and website are managed in separate repositories (some private), but in order to manage tickets through Zenhub, this public repo serves as the coordination point.

## Portal Repository Ecosystem

The PDS portal is composed of multiple repositories, each serving a specific purpose. Below is an overview of all related repositories:

### 🚀 Current Production

- **[portal-infra](https://github.com/NASA-PDS/portal-infra)** - CMS for the PDS home page using Drupal
  - The current production implementation of pds.nasa.gov
  - Leverages the Web Strategy Team's Docker Drupal Demo as a starting point
  - Integrates with PDS Web Design System (WDS) packages
  - Uses GitHub Actions for automated deployment to NASA Mission Cloud Platform (MCP)
  - Note: The main implementation code is in a private `portal-drupal` repository

- **[portal-wst-docker-drupal](https://github.com/NASA-PDS/portal-wst-docker-drupal)** - Local development environment
  - Simplifies local development of Drupal modules for `portal-infra`/`portal-drupal`
  - Uses the Web Strategy Team's docker-drupal codebase
  - Includes services: Apache, PHP 8.3, MySQL 8.0, Solr 8, Chrome

- **[portal-search](https://github.com/NASA-PDS/portal-search)** - Data Catalog search interface
  - A simplified search interface for NASA's CMR (Common Metadata Repository) Data Catalog
  - Built with Node.js and Vite
  - Provides search functionality integrated into the portal
  - Homepage: [https://www.earthdata.nasa.gov/data/catalog](https://www.earthdata.nasa.gov/data/catalog)

- **[portal-search-ui-legacy](https://github.com/NASA-PDS/portal-search-ui-legacy)** - Legacy Keyword Search UI
  - Legacy search interface querying the Legacy Registry through Apache Solr
  - Tomcat-based application packaged as a WAR file
  - Requires Apache Tomcat 8.5+ and Legacy Registry with Apache Solr
  - Homepage: [https://pds.nasa.gov/datasearch/keyword-search/](https://pds.nasa.gov/datasearch/keyword-search/)

- **[portal-ds-view](https://github.com/NASA-PDS/portal-ds-view)** - Data Set View application
  - Browse interface for PDS context products
  - Tomcat-based application packaged as a WAR file
  - Deployed at pds.nasa.gov/ds-view
  - Built with Maven, includes Docker support

### 📚 Legacy/Historical

- **[portal-legacy](https://github.com/NASA-PDS/portal-legacy)** - Previous PDS.nasa.gov website
  - The original/legacy implementation of pds.nasa.gov
  - Static HTML/CSS/JS website

- **[portal-legacy-docker](https://github.com/NASA-PDS/portal-legacy-docker)** - Docker configuration for portal-legacy
  - Docker configuration to run the portal-legacy site locally for testing
  - Uses git submodules to pull in the portal-legacy repository

- **[portal-wp](https://github.com/NASA-PDS/portal-wp)** - **DEPRECATED** WordPress implementation
  - Previous WordPress-based implementation of the PDS portal
  - Superseded by the Drupal-based portal-infra
  - Served as the intermediate step between portal-legacy and the current Drupal implementation

- **[portal-wp-tasks](https://github.com/NASA-PDS/portal-wp-tasks)** - Template/placeholder repository
  - Originally intended for WordPress portal tasks
  - Now points to the [PDS Web Design System](https://github.com/NASA-PDS/pds-wds) repository
  - Primarily a template/placeholder repo

## Portal Evolution Timeline

```
portal-legacy (Static HTML)
    ↓
portal-wp (WordPress) [DEPRECATED]
    ↓
portal-infra/portal-drupal (Drupal) [CURRENT]
```

## Related Resources

- **[PDS Web Design System (WDS)](https://github.com/NASA-PDS/wds)** - React-based CSS implementation for PDS Design System
- **[WDS React](https://github.com/NASA-PDS/wds-react)** - React component library based on the Horizon Design System
- **[Web Strategy Team Docker Drupal Demo](https://github.com/Web-Strategy-Team/Docker-Drupal-Demo)** - Base infrastructure for the current portal

## Getting Started

### For Content Updates or Feature Requests
Create an issue in this repository (portal) to track requests for the pds.nasa.gov website.

### For Development
- **Current portal development**: See [portal-infra](https://github.com/NASA-PDS/portal-infra) and [portal-wst-docker-drupal](https://github.com/NASA-PDS/portal-wst-docker-drupal)
- **Search functionality**: See [portal-search](https://github.com/NASA-PDS/portal-search)
- **Tomcat applications**: See [portal-search-ui-legacy](https://github.com/NASA-PDS/portal-search-ui-legacy) and [portal-ds-view](https://github.com/NASA-PDS/portal-ds-view)
- **Legacy site testing**: See [portal-legacy-docker](https://github.com/NASA-PDS/portal-legacy-docker)

## Support

For questions or issues related to the PDS portal, please open an issue in this repository.
