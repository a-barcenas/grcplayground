# FIPS 199 categorization record

Completed 16 October 2026 in GRC Playground.

## BenefitPortal

SC BenefitPortal = {(confidentiality, HIGH), (integrity, MODERATE), (availability, MODERATE)}
Overall: High

Information types: applicant identity and income records (confidentiality raised from Moderate to High), eligibility determinations, public program information.

- Confidentiality (High): Applicant identity and income records, raised from Moderate to High: about two million people's SSNs and income in one place would cause severe harm if they leaked together.
- Integrity (Moderate): Eligibility determinations, kept at Moderate: a caseworker checks every decision before payment and applicants can appeal, so an error is serious but caught.
- Availability (Moderate): Eligibility determinations, Moderate: an outage stops applications and decisions, which is serious for applicants but recoverable.

## InternalScheduler

SC InternalScheduler = {(confidentiality, LOW), (integrity, LOW), (availability, LOW)}
Overall: Low

- Confidentiality (Low): No PII and not exposed externally.
- Integrity (Low): Minimal potential schedule conflicts.
- Availability (Low): Minimal, resorting to alternative means for conferences.

## EmergencyAlertSystem

SC EmergencyAlertSystem = {(confidentiality, LOW), (integrity, HIGH), (availability, HIGH)}
Overall: High

- Confidentiality (Low): Little harm. The same closures go out to the public within the hour, and the staging point moves with the response.
- Integrity (High): The crew acts on it before anyone can correct it, and someone could be badly hurt or killed.
- Availability (High): The evacuation order doesn't reach a crew still inside the plume.

## Owner's request

Greg Tolliver, the system owner, asked for Moderate because High adds controls before the March launch. Kept at High: the level follows the harm a leak of two million applicants' records would cause. The cost question goes to control selection, where controls can be tailored with a written reason.

Reviewed and approved by Elena Marsh, Authorizing Official.
