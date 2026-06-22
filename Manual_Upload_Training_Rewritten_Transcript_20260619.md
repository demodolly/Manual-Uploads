# Manual Upload Tool Training - Concise Presenter Script

## Opening

Welcome to the Manual Upload training.

Today we will cover how marketing teams should use the Manual Upload tool, why the process matters, and what you need to prepare before submitting a file.

By the end of this session, you should be able to:

- Identify when manual upload is the right route for your data.
- Classify records correctly as hand raisers or non-hand raisers.
- Prepare the MUSE template with the required privacy, tagging, tracking, and contact data.
- Validate and submit your file through the Manual Upload Request portal.
- Understand what happens to your data after the MRM team receives it.

The goal is simple: we want high-quality, compliant data that can support attribution, reporting, lead scoring, and meaningful seller follow-up.

## Why we use the Manual Upload tool

Manual upload gives marketing teams a controlled way to submit eligible customer engagement data when that data is not already captured through an automated integration.

The tool helps us in four important ways.

First, it standardizes the data we collect. The template guides you to provide the information needed for your specific use case, which reduces guesswork and manual errors.

Second, it protects data quality. The information you provide is used by marketing attribution, funnel reporting, lead scoring, Eloqua, and downstream sales follow-up teams. If the upload is incomplete or incorrectly tagged, those processes are affected.

Third, it supports privacy compliance. We must be clear about whether a contact explicitly asked for sales follow-up, whether we have the right opt-in information, and whether regional consent requirements apply.

Finally, it helps sellers have better conversations. When the activity ID, campaign details, and customer context are clear, sellers understand why they are contacting the customer and what the customer engaged with.

## High Level Process

At a high level, the manual upload process starts before you submit the file.

First, confirm that your data is eligible for manual upload. If required, complete the privacy assessment, gather your campaign tagging and tracking IDs, include any event IDs, and make sure your contact details are ready.

If you need help preparing the MUSE template, or if you have a large volume of data, complete the Demand Intake form. The MRM team will help make sure the template is populated correctly.

If you are confident the template is complete and accurate, submit the Manual Upload Request form. In that request, select the use case you are uploading and attach the completed MUSE template.

MRM will validate the template and prepare the data for upload into the Demand Intake Tool. From there, Tray processes the file, CDF cleanses and enriches contacts and accounts, and standard processing checks are applied. This includes validating IDs, appending additional data attributes, and running suppression rules to confirm whether records are sales ready.

If the file contains hand raisers, and the records pass suppression rules, those leads are sent to the VDC for follow-up and to Eloqua for inclusion in the lead scoring model. If the file contains non-hand raisers, suppression rules still apply, but the records are passed only to Eloqua.

Eloqua then runs the lead scoring model for each transaction. High-scoring leads are passed back to Tray, processed as warm non-hand raiser leads, and validated to determine whether they should be sent to the VDC.

## Architecture - The End to End Journey

This slide shows where your data is stored and how it moves through the end-to-end process.

When Tray processes hand raisers for Cisco proprietary events, paid leads, webinars, and trade shows, valid leads are passed to SFDC for sales follow-up. Those same transactions are also sent to the Eloqua Transaction CDO so they can be included in marketing history and lead scoring.

For non-hand raisers from trade shows and webinars, the records are stored in the Eloqua Registration CDO. These records are not sent directly to sales, but they are still captured for attribution and scoring.

In both paths, the transaction is captured in CDF and processed into the lead scoring model. This ensures the engagement contributes to the customer's overall score and can support future routing if the lead becomes sales ready.

## Deep Dive - The Lead Scoring Model

At a high level, the lead scoring model uses a two-layered approach.

Each lead is evaluated using a matrix that combines a profile score and an engagement score. The profile score is graded from A to D, and the engagement score is graded from 1 to 4, with each score moving in 25-point increments.

The profile score is based on explicit data. This is factual information provided by the customer or known about the contact, such as decision-maker status, job level, department, and whether the email domain is corporate or private.

The engagement score is based on implicit data. This is passively observed activity that helps us infer buyer intent, such as web page visits, form submissions, event attendance, manual uploads, and email activity.

Together, the profile and engagement scores determine the routing outcome. High-scoring combinations, shown in white on the slide, route quickly to SFDC as actionable leads. Lower-scoring combinations remain in Eloqua for continued nurturing until additional engagement or profile changes increase the score.

Full details of the lead scoring model are available on the SharePoint site listed in the reference section at the end of this presentation.

This slide also shows the comprehensive list of Eloqua transactions that are included in the scoring model, so you can see which types of customer engagement contribute to the overall score.

## The most important decision: hand raiser or non-hand raiser

Before you start the template, decide whether the records are hand raisers or non-hand raisers.

A hand raiser is someone who explicitly asked to be contacted by Cisco sales about a specific event, offer, or activity. Hand raisers can be routed for seller follow-up after validation and suppression checks.

A non-hand raiser is someone who engaged with a supported marketing activity but did not explicitly request sales contact. These records are used for attribution and lead scoring. They should not be sent directly to sellers unless they later qualify through the lead scoring process.

This classification is critical. If we upload non-hand raisers as hand raisers, we may contact customers without the correct permission. That creates privacy, legal, and customer trust risks. Only classify a record as a hand raiser when there is clear evidence that the customer asked for sales follow-up for that activity.

## When to use manual upload

Use manual upload only for supported use cases that are not already handled through an automated process.

For hand raisers, supported sources include:

- Third-party trade shows.
- Third-party webinars.
- First-party webinars that are not already integrated.
- Cisco proprietary events where manual upload is the approved route.
- Paid leads.

For non-hand raisers, the supported use cases are currently trade shows and webinars.

Before using manual upload, always check whether your data is already integrated:

- Cisco-owned events are often passed through existing event systems such as Cvent, RainFocus, or related event-status processes.
- PathFactory data and Webex registration data are automatically integrated into Eloqua for attribution and lead scoring.
- Webex attendance records may be uploaded manually, but the event ID must align to the registration so the records can be matched.
- Manual content syndication is no longer required because that process is automated through the Integrate tool.

If your use case does not fit one of the supported paths, contact MRM or the Manual Upload process owner before preparing the file. Do not force the data into a use case that does not match the customer journey.

## What to prepare before completing the template

Before you begin entering data, make sure you have the required approvals and identifiers.

You may need a privacy assessment. Unless your upload is an approved Cisco proprietary event use case, confirm that the correct privacy review has been completed and that opt-in evidence is available where required.

You also need campaign tagging and tracking information:

- Activity ID: required for every upload. This should represent the specific marketing initiative. Use a clear name and description because this information can be visible to sellers and used for reporting.
- Drive-to ID: required for every upload. This identifies the channel or route that drove the engagement.
- Offer ID: required for webinars and optional for some paid lead use cases.
- Event ID: required when the upload relates to an event and should align to the event record in the global meetings and events process.

As previously discussed, if you need help with the template, complete the Demand Intake form and work with MRM. If your file is ready to be uploaded, attach the completed MUSE template in the Manual Upload Request form.

Before we go further, there are a few general formatting and validation rules to keep in mind when using the template.

First, make sure you know whether you are uploading hand raisers or non-hand raisers. That decision determines how the data is processed and whether it can be routed for sales follow-up.

The maximum file size is 6 MB. When MRM uploads your file, they will only upload Sheet 4 - Demand Intake File, so the template structure must remain intact.

Use only one use case per file. If you have more than one use case, prepare separate templates for each one.

Activity IDs and drive-to IDs are mandatory in the file. These IDs are needed for processing, reporting, attribution, and seller context.

When adding contact details, do not cut and paste data. Always copy and paste so formulas are not overwritten, and never delete columns or rows from the template.

## Completing the template

Start on the general upload details tab.

Select whether you are uploading hand raisers or non-hand raisers. The template will show a warning when hand raisers are selected because those records may be routed for direct sales follow-up. Confirm that the customer gave explicit permission before continuing.

Next, select the correct data source and use case. This selection matters because it drives the downstream processing path and supports attribution reporting.

Items shown in grey are for information only. The business use case explains what will happen to your data after upload, while the upload information is mainly for MRM. MRM uses it to load the data into the Demand Intake Tool, which has a mapping structure that is less user-friendly than the MUSE template.

All use cases that are not Cisco proprietary events need a privacy ID to ensure our data uploads comply with Cisco privacy rules.

For webinars, there is an additional question. As with every upload, select the correct use case, data source, and privacy ID.

The template will ask whether your webinar registration was run through Cvent or PathFactory. If it was, do not use the MUSE template because that webinar data is integrated directly into Eloqua from the source.

If your registrations were run through Webex, the registrations are also integrated into Eloqua automatically. In that case, only use the MUSE template for attendance records, and make sure the EID matches the registration data.

Webinar data from other platforms can be uploaded through the Manual Upload process.

Enter the transaction date. Manual uploads must be submitted within 30 days of the event or engagement. Records outside that window may be rejected because they are no longer considered viable for standard processing.

Then enter the required IDs. If one activity ID, drive-to ID, offer ID, or event ID applies to all records, select that option and let the template populate the rows for you. If the file contains multiple activities or events, select the multiple-ID option and complete the highlighted mandatory fields row by row.

For trade shows, answer the booth privacy signage question. If approved privacy signage was displayed prominently with the required language, the template can apply the related consent handling. If signage was not displayed, you must capture email and phone opt-in information separately where required.

For non-hand raiser trade shows, indicate whether everyone in the file attended the event. If everyone attended, the template can populate the attendance value. If only some contacts attended, complete the attendance field for each relevant row.

For webinars, remember that offer ID is mandatory. It allows us to understand webinar performance and connect the engagement to the correct content.

## Entering contact and company data

On the data entry tab, complete the required contact and company fields.

Email address is mandatory. First name and last name should be provided wherever available.

Company name and country are also mandatory. Country must match the standard list of values in the template. Company name is free format, but the more complete and accurate the company information is, the better the matching process will be in CDF.

Job title is free format. Job level and job department must use the standard list of values. These fields help the lead scoring model understand the contact profile.

Address details such as address line, city, state, and postal code are not always mandatory, but they improve account matching and data quality.

If you provide a phone number, keep the phone number and extension in separate fields. Use a clean phone number format, ideally including the international country code. Do not enter values such as "unknown," "not applicable," or placeholder text. If you do not have a phone number, leave the field blank.

Do not cut cells, move columns, delete rows, or change the structure of the template. Enter or paste values into the fields provided so the formulas and validations continue to work.

## Privacy consent and opt-in fields

The opt-in fields are separate from the hand raiser decision.

Hand raiser status tells us whether the customer asked for sales follow-up for this specific activity. Opt-in status tells us whether we can contact the customer for future marketing communications.

For email and phone opt-in fields, use:

- "Y" only when you have an audit trail showing the customer opted in.
- "N" when the customer explicitly opted out.
- Blank when you do not have confirmed opt-in evidence or when the customer only asked to be contacted about this specific activity.

Leaving the field blank is safer than guessing. During processing, the latest consent information available in CDF can be used where applicable.

Some regions have additional consent requirements. For China, cross-border storage and data sharing consent fields may be required. For Korea, Vietnam, and India, combined consent requirements may apply. If the country triggers these fields, the template will highlight them as mandatory. If required consent is missing or set to no, the record may be rejected because we cannot store or process the data.

## Validating the file

When the file is ready, return to the general upload details tab and mark the file as ready for upload.

The template runs validation checks. It checks mandatory fields such as email, company, country, activity ID, drive-to ID, and use-case-specific fields such as offer ID or event ID. It also checks standard list of values for fields such as country, job level, job department, and opt-in responses.

If you see a thumbs-up, the file has passed the template checks and can move to submission.

If you see a thumbs-down, go to the file validations tab. The validation tab will show the row and field that need attention, along with a summary of the issue. Correct the data in the main entry tab, then rerun the validation.

The maximum file size is 6 MB. If your file is larger than that, contact MRM for guidance before submission.

## Submitting the file

After the file passes validation, upload the full MUSE template through the Manual Upload Request portal.

MRM will take over from there. They will review the file, perform additional checks, prepare the upload-ready sheet, submit it for processing, and confirm when the upload has been completed.

You will receive processing results showing how many records passed and how many failed. Failed records may be due to missing required data, invalid values, suppression rules, duplicates, unsupported countries, employee or partner exclusions, or other data quality rules.

## Why data quality matters downstream

Poor data quality has real consequences.

If tagging and tracking IDs are missing or incorrect, campaign attribution is weakened. Activity IDs connect to campaigns and programs. Drive-to IDs connect to channels and vehicles. Offer IDs connect to specific content. If those IDs are wrong, reporting cannot accurately show the impact of the marketing activity.

If activity names and descriptions are too vague, sellers lose context. A specific description such as "Supercomputing 2026 event in St. Louis" helps a seller understand the customer interaction. A vague description such as "customer event" or "Webex in Mumbai" does not give enough information for a useful follow-up conversation.

Good data protects Cisco's credibility with customers. When sellers know exactly what a customer engaged with, the follow-up feels relevant and professional. When the data is vague or inaccurate, sellers may abandon the lead or have a poor-quality conversation.

Most importantly, correct classification protects customer trust. Hand raisers and non-hand raisers must be handled differently. If we get that wrong, we risk contacting customers in a way they did not agree to.

## What MRM does after submission

Most of the downstream processing is handled by MRM and the automated workflow.

MRM reviews the file, checks general data quality, and prepares the upload-ready tab from the MUSE template. They submit the file using the data source and business use case you selected in the template.

During processing, Tray applies suppression and routing rules. These can include checks for employees, partners, duplicates, missing surname or company name, unsupported countries, and missing tagging or tracking IDs.

For hand raisers, Tray also checks the customer's consent status and country rules to determine whether the record is sales ready. Only records that pass the required checks continue through the appropriate sales routing path.

## Closing

To summarize:

- Use manual upload only for supported use cases that are not already automated.
- Classify records correctly as hand raisers or non-hand raisers.
- Prepare privacy evidence, activity IDs, drive-to IDs, offer IDs, event IDs, and vendor details before starting.
- Complete the MUSE template without changing its structure.
- Use the validation tab to fix errors before submission.
- Submit the file through the Manual Upload Request portal and wait for MRM confirmation.

Manual upload is a small step in the marketing workflow, but it has a large downstream impact. When we prepare the data correctly, we improve reporting, protect privacy, support lead scoring, and give sellers the context they need to follow up effectively.
