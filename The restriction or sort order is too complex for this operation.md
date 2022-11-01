When you get the error "The restriction or sort order is too complex for this operation" when using a Filter and a Orderby query to for example orderby ReceivedDateTime 
when using a Filter (because you want the last email to be returned first)

Make sure that ReceivedDateTime is included in the filter as the first clause eg

    Get-MgUserMailFolderMessage -UserId mailbox@domain -MailFolderId inbox -Filter
        "ReceivedDateTime ge 2022-01-01T00:00:00Z and Subject eq 'Test Subject' and hasAttachments eq true and isRead eq false"
        -Top 1 -orderby 'ReceivedDateTime  DESC'
