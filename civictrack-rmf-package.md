# CivicTrack RMF package

Completed 16 October 2026 in GRC Playground.

## System

CivicTrack Analytics: internal incident analytics for internal staff, hosted in AWS.

## Categorize

- Objective compromised if case notes leak (your call): Confidentiality
- Overall categorization: Moderate, the FIPS 199 high-water mark across CivicTrack's information types

## Boundary

- In the system: CivicTrack Web Application, Application Server, Database, Object Storage, Admin Access Node
- Inherited: Identity Provider (SSO), Logging Platform
- External: External Reporting Tool

## Select

- Baseline: NIST SP 800-53B Moderate, which follows from the categorization
- Risks matched to control families:
  - Someone signs in to CivicTrack with a stolen password: Identification & Authentication
  - Security teams need to investigate suspicious activity: Audit & Accountability
  - A vulnerability requires coordinated response actions: Incident Response
  - Administrators must enforce secure system settings: Configuration Management

## Implement

- Where each control's evidence lives:
  - Multi-factor authentication enforced: Identity provider configuration
  - System logs captured: Logging platform records
  - Access privileges restricted: Role configuration or access control lists

## Assess

- Finding: In identity-config.yaml you found skip_mfa_on_trusted_network: true, which let admins on the office network sign in with a password alone, and wrote it up as F-001.

## Authorize

- Recommendation: Authorize to operate, with conditions to close the two findings on their POA&M dates
- Reason: Security risk minimal due to internal access required.

## Monitor

- Finding: You traced four days of missing audit events to the logging platform's token rotation, which CivicTrack's forwarder never picked up.

## The critical vulnerability

- What went to the AO: A POA&M entry with an owner and a three-week date, the export feature switched off in the meantime, and a request for Marcus to accept the risk until then.
