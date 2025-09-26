# [Simpler.Grants.gov](https://simpler.grants.gov/)

A modernization effort for [Grants.gov](https://grants.gov/)

## About the Project

We want Grants.gov to be an extremely simple, accessible, and easy-to-use tool for posting, finding, sharing, and applying for federal financial assistance. Our mission is to increase access to grants and improve the grants experience for everyone. We’re improving the way applicants search for and discover funding opportunities, making it easier to find and apply. For federal grantmaking agencies, we’re making it easier for their communities to find the funding they need.

Go to [Simpler.Grants.gov](https://simpler.grants.gov/) to learn about our transparent process and what we’re doing now, or explore our existing user research and the findings that are guiding our work.

See [goals.md](./documentation/goals.md) for more information about the vision and goals for the project.

## Core Team

The core team on the grants.gov project is a small group of content strategists, designers, developers, and product managers working for and with the Department of Health and Human Services, and other federal agencies, and community volunteers.

An up-to-date list of core team members can be found in [MAINTAINERS.md](./MAINTAINERS.md). At this time, the project is still building the core team and defining roles and responsibilities. We are eagerly seeking individuals who would like to join the community and help us define and fill these roles.

## Repository Structure

- [./.github](./.github) contains Github specific settings files and testing, linting, and CI/CD workflows
- [./api](./api) contains an API built in Python using the Flask library
- [./bin](./bin) contains scripts for managing infrastructure
- [./documentation](./documentation) contains project guides, documentation, and decision records
- [./frontend](./frontend) contains a web application built using Next.js
- [./infra](./infra) contains Terraform modules and configuration for managing the AWS infrastructure
- [./scripts](./scripts) contains grants scanning and tracking toolkit scripts

## Grants Scanning and Tracking Toolkit

This repository includes a comprehensive toolkit for scanning, recording, and tracking federal grants and applications. The toolkit provides automated scanning of Grants.gov opportunities, local tracking of applications and responses, and evidence collection capabilities.

### Quickstart Guide

1. **Setup Environment:**
   ```bash
   # Install dependencies
   pip install -r requirements.txt
   
   # Copy environment template
   cp .env.example .env
   
   # Edit .env file with your configuration
   ```

2. **Scan for Grant Opportunities:**
   ```bash
   python scripts/scan_grants.py
   ```

3. **Track Applications and Responses:**
   ```bash
   # Add a new application
   python scripts/submit_tracker.py add-application --opportunity-id GRANT-123 --applicant applicant_name
   
   # Record a response
   python scripts/submit_tracker.py add-response --application-id 1 --status denied --evidence-file denial_letter.pdf
   ```

4. **Export Reports:**
   ```bash
   python export_reports.py --output reports/
   ```

### Key Features

- **Automated Scanning**: Daily automated scanning of Grants.gov with GitHub Actions
- **Local Tracking**: SQLite database for tracking opportunities, applications, and responses
- **Evidence Collection**: Systematic collection and archiving of denial/acceptance letters
- **CSV Exports**: Generate reports for legal evidence or analysis
- **Security**: Proper exclusion of sensitive data from version control

For detailed documentation, see [denial-tracker.md](./denial-tracker.md).

## Development

### API

Documentation for the API is linked to from the [API README.md](./api/README.md). For installation instructions, see the [development documentation](./documentation/api/development.md).

### Front-end

Documentation and development instructions for the front-end are provided in the [Front-end README.md](./frontend/README.md).

## Contributing

Thank you for considering contributing to an Open Source project of the US
Government! For more information about our contribution guidelines, see
[CONTRIBUTING.md](CONTRIBUTING.md) to learn more and join our community see our [wiki](https://wiki.simpler.hhs.gov).

## Security

For more information about our Security, Vulnerability, and Responsible
Disclosure Policies, see [SECURITY.md](SECURITY.md).

## Authors and Maintainers

For more information about our Authors and maintainers, see [MAINTAINERS.md](MAINTAINERS.md).

A full list of [contributors](https://github.com/HHS/simpler-grants-gov/graphs/contributors) can be found on GitHub.

## Public domain

This project is licensed within in the public domain within the United States,
and copyright and related rights in the work worldwide are waived through the
[CC0 1.0 Universal public domain
dedication](https://creativecommons.org/publicdomain/zero/1.0/).

All contributions to this project will be released under the CC0 dedication. By
submitting a pull request or issue, you are agreeing to comply with this waiver
of copyright interest.
