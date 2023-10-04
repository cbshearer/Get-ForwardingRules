# Get-ForwardingRules
This is a script to check and report on all 6 of the mailbox parameters for forwarding &amp; redirecting.
3 of the methods are properties of the mailbox:
  ForwardingAddress 
  ForwardingSmtpAddress
  DeliverToMailboxAndForward
3 of the methods are types of rules :
  DeliverToMailboxAndForward
  ForwardingSmtpAddress
  ForwardingAddress

This script will do the following:
  1. connect to your Microsoft Online / Exchange Online Management
  2. get all mailboxes in the environment (with get-EXOMailbox) (Note: this can take some time in large environments)
  3. Loops through all mailboxes, looking for the 2 mailbox properties and the 3 forwarding rules
  4. If mailboxes with results are found, they are added to a log file (configured on line 12)
  5. The following information is incleded in the log file:
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
