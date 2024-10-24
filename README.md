Feature: Gmail Compose  As a user I want to compose and send emails So that I can communicate with others.

Scenario: Successful Email Composition
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I click "Send"
  Then the email is sent successfully

Scenario: Empty Subject
  Given I am logged in to Gmail
  When I compose an email with empty subject and body "QA test for Incubyte"
  And I click "Send"
  Then an error message is displayed for empty subject

Scenario: Empty Body
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and empty body
  And I click "Send"
  Then the email is sent successfully

Scenario: Invalid Recipient
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I enter invalid recipient email
  And I click "Send"
  Then an error message is displayed for invalid recipient

Scenario: Network Connection Issue
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I click "Send" without internet connection
  Then an error message is displayed for network connection issue

Scenario: Attachment
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I attach a file
  And I click "Send"
  Then the email is sent successfully with attachment

Scenario: CC/BCC
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I add CC/BCC recipients
  And I click "Send"
  Then the email is sent successfully to CC/BCC recipients

Scenario: Draft Save
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I click "Save draft"
  Then the email is saved as draft

Scenario: Cancel Composition
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I click "Discard"
  Then the email composition is cancelled

Scenario: Multiple Recipients
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I enter multiple recipient emails
  And I click "Send"
  Then the email is sent successfully to all recipients33

Scenario: Invalid Recipient
  Given I am logged in to Gmail
  When I compose an email with subject "Incubyte" and body "QA test for Incubyte"
  And I enter invalid recipient email
  And I click "Send"
  Then an error message is displayed for invalid recipient

Scenario: Empty Subject and Body
  Given I am logged in to Gmail
  When I compose an email with empty subject and body
  And I click "Send"
  Then an error message is displayed for empty subject and body

Scenario: Exceeding Character Limit
  Given I am logged in to Gmail
  When I compose an email with subject exceeding 255 characters
  And I enter body exceeding 20,000 characters
  And I click "Send"
  Then an error message is displayed for exceeding character limit

Scenario: Attachment Size Limit
  Given I am logged in to Gmail
  When I compose an email with attachment larger than 25MB
  And I click "Send"
  Then an error message is displayed for attachment size limit

Scenario: Invalid File Type
  Given I am logged in to Gmail
  When I compose an email with attachment of invalid type
  And I click "Send"
  Then an error message is displayed for invalid file type
