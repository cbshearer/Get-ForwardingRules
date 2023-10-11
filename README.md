# Get-ForwardingRules
This is a script to check and report on all 6 of the mailbox parameters for forwarding &amp; redirecting.

3 of the methods are properties of the mailbox:
  - ForwardingAddress 
  - ForwardingSmtpAddress
  - DeliverToMailboxAndForward

3 of the methods are types of rules :
  - DeliverToMailboxAndForward
  - ForwardingSmtpAddress
  - ForwardingAddress

This script will do the following:
  1. Connect to your Microsoft Online / Exchange Online Management
  2. Get all mailboxes in the environment (with get-EXOMailbox) (Note: this can take some time in large environments)
  3. Loops each mailbox looking for the mailbox properties used for automatic forwarding
  5. In each mailbox, loops through all email rules on each mailbox looking for the 3 types of rules used for automatic forwarding
  6. If mailboxes with results are found, they are added to a log file (configured on line 12)
  7. The following information is incleded in the log file:
     - Email Address
     - User display name
     - Rule priority (if a rule)
     - Rule description (if a rule)
     - Rule ID (if a rule)
     - Rule enabled status (if a rule)
     - Rule name (if a rule)
     - Forwrad to address (if a forwarding rule)
     - Redirect to address (if a redirect rule)
     - Forward as attachment to address (if a forward as attachment rule)
     - Deliver to mailbox aand Forward address (if that mailbox property)
     - Forwrading Smtp Address (if that mailbox property)
     - Forwarding Address (if that mailbox property)
