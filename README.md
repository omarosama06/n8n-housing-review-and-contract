# Housing Application Review and Contract Workflow (n8n)

Part of a team project that automates a social housing application
process. This workflow covers the employee review, apartment
allocation and contract generation stages.

## How it works
1. **Review:** an email goes to a reviewer with the applicant's
   details, and the workflow waits for an Approve or Reject reply
2. **Allocation:** if approved, it looks up the first available
   apartment in a Google Sheet
3. **Reservation:** the apartment is marked as Reserved for the
   applicant in the sheet. If none are left, the workflow stops
4. **Contract:** a contract template (Google Docs) is copied and
   filled with the applicant and apartment details, then exported
   as a PDF and saved to a Drive folder
5. **Output:** the workflow returns the contract link and
   apartment details

## Tools used
n8n, Gmail (send and wait for approval), Google Sheets,
Google Docs, Google Drive

## How to run it
1. Import `housing-workflow.json` in n8n
   (Workflows → Import from file)
2. Connect your own Gmail, Google Sheets, Docs and Drive credentials
3. Replace the placeholders: `YOUR_GOOGLE_SHEET_ID`,
   `YOUR_DRIVE_FOLDER_ID`, `YOUR_CONTRACT_TEMPLATE_ID` and the
   reviewer email
4. Create an Apartments sheet with the columns ApartmentID,
   Building, City, Status, ReservedFor and NationalID
5. Create a contract template with these placeholders:
   {{FULL_NAME}}, {{NATIONAL_ID}}, {{APARTMENT_ID}}, {{BUILDING}},
   {{DATE}}
6. Run it manually. The test applicant uses sample data

## Notes
The first stage (application intake and screening) was built by a
teammate. This workflow starts from a test applicant for
demonstration.

## Screenshot
<img width="1153" height="582" alt="Housing" src="https://github.com/user-attachments/assets/5df86b43-7dbe-4a61-ad8a-e74e40256d0b" />
